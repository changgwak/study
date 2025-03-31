Cartographer SLAM에 대해 전문가 수준으로 설명드릴게요. 😎  

---

## ✅ Cartographer SLAM이란?

**Cartographer**는 구글에서 개발한 **2D 및 3D SLAM (Simultaneous Localization and Mapping)** 시스템입니다. 로봇이 **센서를 기반으로 주변 환경의 지도를 생성하고, 동시에 자신의 위치를 추정**할 수 있게 해줍니다.

SLAM 문제는 본질적으로 "내가 어디 있는지 모르겠고, 지도가 없다. 그런데 지도를 만들면서 내 위치도 알고 싶다"라는 역설적인 문제입니다. Cartographer는 이를 **정확하고, 실시간으로** 해결합니다.

---

## 📦 Cartographer의 핵심 구성 요소

### 1. **Sensor Bridge**
- ROS의 센서 데이터를 Cartographer 내부 포맷으로 변환.
- 예) `sensor_msgs/LaserScan`, `sensor_msgs/Imu`, `nav_msgs/Odometry` → Cartographer 내부 메시지 타입으로 변환

### 2. **Trajectory Builder**
- 로봇의 이동 경로를 추정하면서 서서히 맵을 쌓아가는 부분.
- **Local SLAM**: 센서 데이터를 기반으로 로봇의 짧은 이동 경로 추정 (fast)
- **Pose Graph Optimization (Global SLAM)**: 전체 경로를 그래프로 구성하고 최적화 (slow but accurate)
- 노드와 엣지로 구성된 **pose graph**를 통해 loop closure 수행 가능

### 3. **Map Builder**
- 여러 trajectory를 합쳐서 하나의 큰 맵 생성.
- loop closure와 global consistency 확보.

---

## 📐 사용 센서 예시

- **LIDAR** (2D 또는 3D)
- **IMU**
- **Odometry** (wheel encoder 기반)
- RGB-D 카메라 (3D에서 가능하지만 완벽 지원은 아님)

---

## ⚙️ ROS2에서 Cartographer 사용 흐름

1. **센서 준비 및 드라이버 연결**  
   LIDAR, IMU, Odom 데이터를 토픽으로 발행되게 준비합니다.

2. **Cartographer Configuration File 작성**  
   `.lua` 포맷으로 SLAM 세부 설정 지정  
   (예: `use_imu_data = true`, `num_laser_scans = 1` 등)

3. **Launch File 구성**  
   `cartographer_ros`의 launch 파일을 사용하거나 수정  
   (예: `cartographer_ros/cartographer_ros/launch/demo_revo_lds.launch.py`)

4. **실행 및 시각화**  
   Rviz2에서 `/map`, `/tf` 등 시각화  
   또는 `ros2 bag`으로 데이터 기록 및 offline mapping 가능

---

## 🧠 Cartographer의 장점

- **Loop closure** 자동 처리 → 정확한 맵 생성
- **IMU + LIDAR + Odom**을 자연스럽게 융합
- **2D 및 3D SLAM 모두 지원**
- 실시간 처리 가능 (local SLAM) + 고정밀도 보정 (global SLAM)

---

## ⚠️ 주의사항 및 한계

- 환경에 따라 loop closure가 잘 안 될 수 있음
- 파라미터 튜닝 필요 (특히 `accumulated_range_data` 관련 설정)
- 메모리 사용량이 높을 수 있음 (특히 3D SLAM)

---

## 📍요약

| 항목 | 설명 |
|------|------|
| 주요 센서 | LIDAR, IMU, Odometry |
| SLAM 종류 | 2D/3D 실시간 Mapping + Localization |
| ROS2 통합 | `cartographer_ros` 패키지 사용 |
| 핵심 기능 | Loop Closure, Pose Graph, Real-Time Mapping |
| 필요 설정 | `.lua` 파라미터 파일, Launch 설정 |

---

필요하다면 `.lua` 설정 예시, launch 구성, 또는 실시간 튜닝 팁도 알려드릴게요.  


<br>
<br>
<br>
<br>
<br>
<br>


센서와 알고리즘 기반으로 **Cartographer의 동작 구조**와 **pure localization 모드 사용 시 흐름**을 더 깊이 설명드릴게요.

---

## 📦 Cartographer 핵심 구조 – 상세 설명

### 1. **Sensor Bridge**

Cartographer는 ROS 메시지를 내부 포맷으로 바꿔야 처리가 가능합니다. 여기서 **Sensor Bridge**가 역할을 합니다.

- `sensor_msgs/LaserScan` → Laser 데이터로 변환
- `sensor_msgs/Imu` → 내부 IMU 포맷으로 변환 (orientation, angular velocity 등)
- `nav_msgs/Odometry` → odom 기반 pose estimate로 변환

**시스템 구성:**
- `wit_imu_driver` + `imu_filter_madgwick` → `/imu/data`로 필터링된 orientation 제공
- `roboteq_diff_driver` → `/wheel/odometry` 제공
- `robot_localization (EKF)` → `/odometry/filtered` 제공 → Cartographer에 입력 (odom raw data가 cartographer에 전달되는 것으로 알고 있음.)
- `SICK nanoScan3` → `/scan` → LaserScan 입력

> `cartographer_ros`에서는 이 모든 토픽을 `.lua`에서 지정하여 처리합니다.

---

### 2. **Trajectory Builder**

로봇이 움직일 때 Cartographer는 현재 pose를 추정하고, 이를 기반으로 **local map**을 점점 확장합니다.

- **Local SLAM (Front-end)**  
  빠르게 pose 추정 (LIDAR scan matching, IMU integration 포함)  
  → 아직 global consistency는 고려 X

- **Global SLAM (Back-end, Pose Graph Optimization)**  
  일정 시간마다 pose들을 연결해서 **Pose Graph** 구성  
  → loop closure로 그래프 최적화  
  → 오차 누적 최소화

> 즉, 실시간 추정은 Local SLAM, 고정밀 보정은 Global SLAM이 담당합니다.

---

### 3. **Map Builder**

- 여러 개의 trajectory를 병합하여 전체 맵 구성
- 각 trajectory의 pose들을 global하게 정렬 → 맵 품질 향상
- loop closure detection + optimization 수행

---

## 🧭 Pure Localization 모드란?

**Pure Localization**은 이미 만들어진 맵을 기준으로 **현재 위치만 추정**하는 모드입니다.  
즉, 새로운 map은 생성하지 않고 기존 map에서 위치만 지속적으로 보정합니다.

### 🔄 동작 흐름:

1. **초기 위치 `/initialpose` 주입** 필요  
   → 대략적인 위치와 방향 정보 입력

2. 이후 Cartographer는 다음을 기반으로 현재 pose 추정:
   - LIDAR scan → 기존 map과 매칭
   - IMU → orientation 보정
   - Odometry → 전방향 추정 도움

3. 새 scan이 들어올 때마다 scan-matching을 통해 위치를 추정  
   → 계속해서 `tf`에서 `map → odom` 변환 브로드캐스팅

### 💡 특징:

- SLAM이 아닌 localization-only → `trajectory_builder_xd.lua`에서 `pure_localization = true`로 설정
- loop closure 등은 사용 안 함
- 실시간성과 안정성이 중요 → map 품질, IMU/odom 정확도에 영향받음

---

## 🎯 당신의 AMR 시스템과의 연결

| 요소 | 연결 역할 |
|------|------------|
| `imu_filter_madgwick` | IMU의 yaw drift 보정 → orientation 정확도 ↑ |
| `robot_localization` (EKF) | IMU + Odom 융합 → 부드럽고 안정적인 `/odometry/filtered` 제공 |
| `cartographer_ros` | SLAM/Localization 핵심. pure localization에서 기존 map 기반 위치 추정 |
| `RPP` (local planner) | Cartographer가 추정한 로봇 위치 기반 실시간 궤적 생성 |
| `Theta*` (global planner) | map을 기반으로 최적 경로 생성 |
| RealSense D435 | SLAM엔 직접적 사용 안 하지만 obstacle avoidance나 perception에 사용 가능 |

---

## 📁 `.lua` 설정 관련 팁

**pure localization을 위한 핵심 설정:**

```lua
-- trajectory_builder.lua
TRAJECTORY_BUILDER_2D.pure_localization = true
POSE_GRAPH.optimize_every_n_nodes = 0  -- global optimization 비활성화

-- launch file에서 `load_state_filename`으로 저장된 map state 로딩
```

**launch 예시:**

```bash
ros2 launch my_cartographer_pkg pure_localization.launch.py \
    load_state_filename:=/path/to/my_map.pbstream
```

---

필요하시면 `.lua`, `.launch.py` 예시나 map 저장 (`.pbstream`) 및 불러오기 전체 워크플로우도 알려드릴게요.

다음 질문은 어떤 걸 도와드릴까요?
- `.lua` 설정 튜닝?
- map 저장/불러오기?
- initial pose 자동 주입 방법?
- localization 안정성 높이는 팁?
- Cartographer vs AMCL 비교?


<br>
<br>
<br>
<br>
<br>
<br>


Cartographer SLAM의 **Trajectory Builder**, 특히 **Local SLAM (Front-end)** 과 **Global SLAM (Back-end)** 의 차이와 내부 작동 방식을 더 자세히, 구조적으로 설명드릴게요.

---

## 🧠 1. 전체 구조 요약

Cartographer는 크게 두 단계로 Pose(자세)를 추정합니다:

| 단계 | 이름 | 역할 | 처리 속도 | 주요 기술 |
|------|------|------|------------|------------|
| 1 | **Local SLAM** (Front-end) | 빠르게 pose 추정 | 매우 빠름 (실시간) | Scan Matching, IMU Integration |
| 2 | **Global SLAM** (Back-end) | 전체 궤적 최적화 | 느림 (비실시간) | Pose Graph Optimization, Loop Closure |

---

## 🛰️ 2. Local SLAM (Front-End) – 실시간 위치 추정

### 📍 목적:
- 새로운 센서 데이터가 들어올 때마다 로봇의 현재 위치를 빠르게 추정.
- 실시간 처리 → navigation, obstacle avoidance 등에 바로 활용 가능.

### 🔧 사용되는 입력:
- **LIDAR scan** (`sensor_msgs/LaserScan`)
- **IMU orientation + angular velocity** (`sensor_msgs/Imu`)
- (선택적으로) **Odometry** (`nav_msgs/Odometry`)

### 🔁 처리 순서:

1. **IMU Integration (초기 orientation 예측)**  
   IMU의 angular velocity + orientation을 이용해  
   대략적인 회전량(Orientation) 예측  
   → 예: Cartographer가 “지금 조금 왼쪽으로 돌았군” 하고 예측

2. **LIDAR Scan Matching**  
   현재 LIDAR scan을 이전 scan 또는 submap과 비교하여 best-fit pose 추정  
   - 알고리즘: **Real-Time Correlative Scan Matching (RTCSM)**  
   - 결과: x, y, θ (2D pose) 추정  
   - RTCSM은 빠르지만 coarse하고, 이후 **Ceres Scan Matcher**로 fine tuning 진행

3. **Local Submap에 삽입**  
   추정한 pose와 scan 데이터를 현재 submap에 삽입  
   → 일정 수 이상 쌓이면 submap은 고정되고 새로운 submap 시작

### 🗺️ 결과:
- 실시간으로 현재 위치 (`local_pose`) 제공  
- 완성된 submap은 global SLAM에 전달

---

## 🌍 3. Global SLAM (Back-End) – Pose Graph 최적화

### 📍 목적:
- 여러 submap과 로봇 pose들을 연결하여 전체 trajectory 최적화
- loop closure를 통해 drift 보정

### 🔧 구성 요소:
- **Pose Graph** = 노드 + 엣지
  - 노드: 로봇의 각 시점의 pose
  - 엣지: 센서 간 관계 (e.g. LIDAR scan-matching 결과, odom 등)

### 🔁 처리 순서:

1. **노드 추가**  
   일정 수의 scan이 들어오면 새로운 pose 노드 생성

2. **엣지 추가**  
   - 최근 pose ↔ 이전 pose 간 scan-matching 관계 저장
   - odometry, IMU 정보 등도 관계로 추가

3. **Loop Closure 탐색**  
   - 예전 submap과 현재 scan을 비교하여 “비슷한 위치인가?” 판단
   - 비슷하면 loop closure 제안 → 추가적인 엣지로 연결

4. **최적화**  
   - 전체 Pose Graph를 **Ceres Solver**로 최적화
   - 목적: 위치 누적 오차(drift)를 최소화하고 전체 맵 품질 향상

### 🗺️ 결과:
- 전체 pose와 submap의 위치가 global consistency를 갖도록 정렬됨
- 맵 왜곡이 점점 보정되고, 실제 환경과 유사한 맵이 만들어짐

---

## 📸 비유로 이해하기

- **Local SLAM**은 로봇이 “지금 눈 앞만 보고” 걷는 것  
  → 실시간이지만, 과거를 돌아보지 않음

- **Global SLAM**은 로봇이 “지나온 길을 회고하면서, 전체 지도를 다시 정리”하는 것  
  → 더 정확하지만 느림

---

## 💡 당신의 AMR에 적용하면?

| 구성 요소 | 역할 |
|-----------|------|
| `wit_imu_driver + imu_filter_madgwick` | Local SLAM에서 초기 orientation 예측에 사용됨 |
| `robot_localization (EKF)` | odometry 안정화 → pose graph에 보조적 input |
| `SICK nanoScan3` | scan matching의 핵심 데이터 → local & global 모두 사용 |
| `Depth Camera D435` | SLAM엔 직접 쓰지 않지만 장애물 회피 등에 사용 가능 |

---

## 🧭 Pure Localization 시에는?

- **Local SLAM만 작동**  
  → 기존 맵 (`.pbstream`)과 scan을 실시간 매칭하여 현재 위치 추정

- **Global SLAM은 꺼짐**  
  - `.lua`에서 `pure_localization = true`  
  - `POSE_GRAPH.optimize_every_n_nodes = 0` → global 최적화 비활성화

- **Loop closure 없음**, submap도 새로 생성되지 않음

---

## 🔧 정리

| 항목 | Local SLAM | Global SLAM |
|------|------------|-------------|
| 속도 | 빠름 (실시간) | 느림 (백그라운드) |
| 기능 | 현재 위치 추정 + submap 생성 | Pose graph 최적화 + loop closure |
| 알고리즘 | RTCSM + Ceres Scan Matcher | Pose Graph + Ceres Solver |
| Pure Localization에서 작동 여부 | ✅ 사용됨 | ❌ 사용 안됨 |

---

다음이 궁금하실 수 있어요:
- Pose Graph와 Loop Closure 시각화 방법
- Cartographer 내부 메시지 흐름 구조 (`trajectory builder`, `pose graph` callback 등)
- `pbstream` 파일 구조 설명
- initial pose 자동 주입 로직

<br>
<br>
<br>
<br>
<br>
<br>


이번에는 `MapBuilder`의 역할을 **내부 구조**, **처리 단계**, 그리고 **loop closure 최적화**의 세부 작동 방식까지 아주 자세히 설명드릴게요.

---

## 🧱 MapBuilder란?

**MapBuilder**는 Cartographer의 핵심 모듈 중 하나로, 다음과 같은 역할을 합니다:

1. 로봇이 생성한 여러 개의 **trajectory**(이동 경로)를 수집  
2. 그 안에 있는 pose들을 연결한 **pose graph**를 생성  
3. **loop closure** 감지  
4. **최적화 (pose graph optimization)** 수행  
5. 최종적으로 **전역적으로 정렬된, 일관성 있는 지도(submap mosaic)** 생성

이 과정을 통해 drift가 누적된 경로들을 다시 정렬해서 **정확한 맵**을 완성합니다.

---

## 🔄 전체 처리 흐름

```plaintext
[Sensor Data] 
   ↓
[Trajectory Builder] - Local SLAM, submap 생성
   ↓
[MapBuilder]
   ├── Trajectory 관리
   ├── Pose Graph 생성
   ├── Loop Closure 감지
   ├── 최적화 수행
   ↓
[최종 Map + 정렬된 Trajectories]
```

---

## 🗂️ 1. Trajectory란?

Cartographer에서는 하나의 **trajectory**가 특정 시간 구간 동안 로봇이 만든 경로입니다.  
보통:

- 1개의 로봇 = 1 trajectory
- multi-robot SLAM도 지원 (trajectory 여러 개 병합 가능)

각 trajectory는 다음과 같이 구성됩니다:

| 요소 | 설명 |
|------|------|
| Nodes | 로봇의 pose (x, y, θ) |
| Submaps | 일정 거리 or 스캔 수마다 생성되는 로컬 지도 |
| Constraints | Node ↔ Submap 간 관계. Scan Matching 결과로 생성 |

---

## 🧠 2. Pose Graph란?

Pose Graph는 trajectory의 모든 pose(node)들을 **그래프로 연결**한 구조입니다.

- **Node**: 특정 시간에 로봇이 있던 위치 (Pose + scan)
- **Submap**: 로컬 맵 조각
- **Edge (Constraint)**: 두 node/submap 간의 상대 위치 관계  
  → odom, imu, scan matching으로 생성

```plaintext
     o---o---o---o        ← 로봇이 움직이며 남긴 pose node들
     |   |   |
  submap0   submap1 ...
```

---

## 🔁 3. Loop Closure 감지

### Loop Closure란?

로봇이 **한 바퀴 돌아**서 예전에 지나갔던 지점 근처로 돌아왔을 때,
현재 위치와 예전 위치가 **동일한 장소라는 것을 인식**하는 것.

```plaintext
(시작 지점)
    o----o----o
         |    |
         o----o ← (다시 도착)
```

- Cartographer는 scan을 과거 submap들과 비교
- **scan matching score가 높으면** → loop closure candidate

### 어떻게 감지하나?

- 일정 간격마다:
  - 현재 scan ↔ 과거 submap들과 **Global Scan Matching**
- 잘 맞는 경우:
  - 새로운 **constraint(edge)** 추가 → node ↔ old submap
- 이걸 통해 pose graph에 추가적인 연결이 생기고,
  pose들이 "다시 정렬"되며 드리프트 보정됨

---

## 🔧 4. Pose Graph Optimization (Ceres Solver 사용)

### 목적:
- 모든 node, submap, constraint를 최적화하여
  **전체 pose들이 일관된 위치로 조정**되게 함

### 사용 알고리즘:
- [Ceres Solver](http://ceres-solver.org)라는 고성능 nonlinear least squares solver 사용
- 각 constraint는 에러 함수로 표현됨 → 최소화

### 구성 예시:

```math
Minimize ∑ (ScanMatchError)² + ∑ (OdomConstraintError)² + ∑ (IMUError)²
```

- 각 에러는 “이 node와 submap의 상대 위치는 이 정도 차이가 나야 한다”는 제약
- 최적화 결과: 모든 pose들이 **가장 그럴듯하게 정렬**됨

---

## 📚 실제 예시: Loop Closure 후 Map 정렬 전/후 비교

### BEFORE (loop closure 전)

- submap0: (0,0)
- submap50: (50m, 0)
- submap100: (100m, -2m) → 드리프트 발생

### AFTER (loop closure 감지 및 최적화 후)

- submap0: (0,0)
- submap100: (0,0) 근처로 정렬됨
- 전체 trajectory가 곡선에서 직선으로 조정됨

---

## 💾 MapBuilder의 최종 결과

1. `.pbstream` 파일 (pose graph + submaps 모두 포함)
2. 정렬된 `.pgm` + `.yaml` map (Rviz 등에서 사용 가능)
3. 하나의 일관된 `tf` → `map → odom` transform 생성

---

## ✍️ 요약 표

| 단계 | 역할 | 관련 노드/파일 |
|------|------|----------------|
| Trajectory 생성 | Pose + submap 구성 | `trajectory_builder_2d` |
| Pose Graph 구성 | Node + Constraint 추가 | `pose_graph_2d` |
| Loop Closure 감지 | 예전 submap과 scan 비교 | `constraint_builder` |
| Graph Optimization | 전체 pose 재정렬 | `ceres_solver` |
| 맵 생성 | 정렬된 submap → full map | `MapBuilder`, `.pbstream`, `.pgm` |

---

다음 중 더 알고 싶은 게 있으면 말씀해주세요:

- `pbstream` 내부 구조 (binary 포맷)
- loop closure 실패 시 대처 방법
- multi-trajectory 병합
- pose graph 시각화 (`ros2 topic echo /trajectory_node_list`)
- pure localization에서 pose graph가 어떻게 쓰이는지?

<br>
<br>
<br>
<br>
<br>
<br>

`*.pbstream` 파일은 Cartographer가 만든 **맵과 pose graph 정보를 저장한 binary 포맷**입니다.  
이 파일을 이해하면 SLAM 결과를 복원하거나 분석하거나, pure localization 시 복원할 때도 더 정밀한 컨트롤이 가능해집니다.

---

## 📁 `.pbstream`란?

- **Protobuf 기반 binary stream 파일**
- 내부에는 Cartographer가 사용한 **submap, trajectory, pose graph, sensor data** 등이 포함됨
- SLAM 결과를 저장했다가 pure localization 등에서 **load_state_filename**으로 불러오기 가능

---

## 📦 pbstream 내부 구조 (개요)

.pbstream은 사실상 여러 Protobuf 메시지를 **순서대로 직렬화(serialized)**한 파일입니다.  
주요 구조는 다음과 같습니다:

```plaintext
Repeated entries:
  SerializedData {
    type: "submap" | "node" | "trajectory" | ...
    data: binary blob (protobuf)
  }
```

### 주요 message 종류:

| 타입 | 설명 |
|------|------|
| `Submap` | 로컬 지도의 raw grid 및 위치 정보 |
| `Node` | 특정 시점의 로봇 pose와 sensor data |
| `TrajectoryData` | trajectory에 대한 정보 (id, frozen 여부 등) |
| `PoseGraph` | 전체 노드/서브맵 간의 연결 정보 (constraints) |
| `SensorData` | scan, imu, odometry 등 |
| `AllTrajectoryBuilderOptions` | SLAM 파라미터 설정 값 |
| `Landmark` | (선택적) 위치 기준 랜드마크 정보 |

---

## 🧬 내부 구조 예시 (Protobuf 타입 기준)

### 1. Submap
```protobuf
message SerializedSubmap {
  int trajectory_id
  int submap_index
  Submap2D submap_2d
  ...
}
```
- 로컬 맵 한 조각 (그리드맵 이미지 + 위치 정보 포함)
- pure localization에서도 사용됨

### 2. Node
```protobuf
message SerializedNode {
  int trajectory_id
  int node_index
  transform::Rigid3d pose
  sensor::CompressedPointCloud range_data
}
```
- 로봇이 해당 위치에 있었던 time point 하나
- pose graph 노드로 사용됨

### 3. Constraint
```protobuf
message Constraint {
  int submap_id
  int node_id
  transform::Rigid3d relative_pose
  enum constraint_type { INTRA_SUBMAP, INTER_SUBMAP }
}
```
- scan matching을 통해 형성된 관계
- 최적화 시 사용됨

### 4. TrajectoryData
```protobuf
message TrajectoryData {
  int trajectory_id
  bool frozen  # pure localization 여부
}
```
- mapping 중인지, pure localization인지 여부 표시

---

## 🛠️ pbstream 분석 방법

### 1. `cartographer_pbstream` 도구 사용

```bash
ros2 run cartographer_ros cartographer_pbstream_info \
  -pbstream_filename my_map.pbstream
```

출력 예시:
```plaintext
Trajectory 0:
  120 nodes
  40 submaps
  trajectory frozen: true
```

### 2. `pbstream`을 `.pgm` + `.yaml`로 변환

```bash
ros2 run cartographer_ros cartographer_pbstream_to_ros_map \
  -pbstream_filename my_map.pbstream \
  -map_filestem my_map \
  -resolution 0.05
```

→ `my_map.pgm` + `my_map.yaml` 생성됨

### 3. Protobuf 직접 파싱 (고급)

`.pbstream`은 실제로 `SerializedData` 메시지를 반복적으로 직렬화한 구조입니다.  
C++ 코드에서 다음처럼 접근합니다:

```cpp
cartographer::io::DeserializePoseGraphFromFile(pbstream_path, &pose_graph);
```

또는 Python에서 `protobuf`로 직접 디코딩하려면 `.proto` 파일이 필요하고 꽤 까다롭습니다. 일반적으로는 권장되지 않아요.

---

## 🧭 pure localization에 사용 시

- `cartographer_node`를 실행할 때 `.pbstream`을 로딩하면,
  내부의 **submap + pose graph**가 메모리에 복원됨
- 이후 들어오는 scan과 `.pbstream` 속 submap을 매칭하여 현재 pose 추정

```bash
load_state_filename := /path/to/my_map.pbstream
```

---

## 📁 저장과 불러오기 요약

### 📝 저장
```bash
ros2 service call /write_state cartographer_ros_msgs/srv/WriteState \
"{filename: '/tmp/my_map.pbstream'}"
```

### 📂 불러오기
```bash
ros2 launch cartographer_ros cartographer_ros_launch.py \
load_state_filename:=/tmp/my_map.pbstream
```

`.lua`에서는 반드시 `pure_localization = true` 설정이 포함되어야 함

---

## ✅ 정리

| 항목 | 설명 |
|------|------|
| 포맷 | Protobuf-based binary stream |
| 포함 정보 | submap, node, pose graph, constraint, sensor data 등 |
| 활용 | mapping 저장, pure localization, map 복원 |
| 분석 툴 | `cartographer_pbstream_info`, `cartographer_pbstream_to_ros_map` |
| 고급 분석 | C++ 또는 Python에서 protobuf 직접 디코딩 |

---

필요하시면 `.pbstream` → 시각화 도구 만들기, 자동 분석 스크립트도 도와드릴 수 있어요.  
혹시 `.pbstream`을 다른 포맷으로 변환하거나, 특정 submap만 추출하고 싶으신가요?



<br>
<br>
<br>
<br>
<br>
<br>



# online slam 은 Local SLAM (Front-End) – 실시간 위치 추정 이고  offline slam 은 Global SLAM (Back-End) – Pose Graph 최적화 인지?
 
결론부터 말씀드리면:

✅ **어느 정도 맞는 말이에요**, 하지만 정확하게 이해하려면 약간 보완이 필요해요.  
`online SLAM`과 `offline SLAM`은 **실시간성**과 **데이터 처리 시점**의 차이,  
그리고 Cartographer의 `Local SLAM`과 `Global SLAM`은 **구조적 역할**의 차이입니다.

---

## 🎯 핵심 개념 비교

| 용어 | 정의 | Cartographer 구성 요소와의 대응 |
|------|------|------------------------------|
| **Online SLAM** | 센서 데이터가 들어오자마자 실시간으로 위치 추정 및 맵 생성 | **Local SLAM (Front-End)** + 일부 Global SLAM (background) |
| **Offline SLAM** | 미리 수집된 데이터를 기반으로 전체 맵을 일괄 최적화 | **Pose Graph Optimization (Back-End)** 중심 |

---

## 🧭 용어 구분 자세히 설명

### 🟢 Online SLAM (실시간 SLAM)

- **로봇이 현재 위치를 추정하면서 맵을 만들어 나가는** 방식
- 센서 데이터가 들어올 때마다 빠르게 반응
- LIDAR + IMU + Odom으로 실시간 위치 추정
- 필요시 loop closure도 실시간 시도

📌 **Cartographer에서 online SLAM**은:
- `Local SLAM`이 주 역할 (실시간 scan matching)
- + `Pose Graph Optimization`도 백그라운드 스레드에서 주기적으로 수행됨

👉 그러니까 완전히 Front-end만이 아니라, 일부 Back-end도 포함이에요.  
(단, `optimize_every_n_nodes` 같은 파라미터로 빈도 조절 가능)

---

### 🔵 Offline SLAM (비실시간/후처리 SLAM)

- **ROS bag 등으로 데이터를 수집한 뒤**, 나중에 한꺼번에 맵 생성
- 실시간성이 필요 없음 → 느려도 정밀하게 계산 가능
- 보통 loop closure, pose graph optimization에 초점을 둠

📌 **Cartographer에서 offline SLAM**은:
- `cartographer_offline_node_main` 혹은 `cartographer_rosbag_validate` 사용
- Local SLAM은 scan을 정렬하는 수준
- Global SLAM (pose graph building + 최적화)이 주 작업

---

## 🧩 용어 혼동 주의!

| 용어 | Cartographer 내 대응 | 설명 |
|------|----------------------|------|
| Local SLAM (Front-End) | Online SLAM의 핵심 구성 요소 | 실시간 위치 추정 |
| Global SLAM (Back-End) | Online SLAM에서도 일부 작동 + Offline SLAM의 핵심 | pose graph 최적화, loop closure |
| Online SLAM | 주로 Local SLAM + 일부 Global | 실시간으로 맵 생성 |
| Offline SLAM | 수집된 데이터를 Global SLAM 처리 | 후처리 기반 정밀 맵 생성 |

---

## 예시로 비교

### ✅ Online SLAM:
- 실시간 주행 중
- `/scan`, `/imu`, `/odom` 들어오고
- `map`과 `tf`가 실시간으로 broadcast
- loop closure도 가능 (백그라운드 최적화)

### ✅ Offline SLAM:
- `ros2 bag record`로 데이터 저장
- 나중에 `ros2 bag play` + `cartographer_offline_node`
- loop closure, pose graph 최적화 더 정확하게 수행됨

---

## ✅ 결론

> 당신이 말한:
> - ✅ “Local SLAM = online” → **부분적으로 맞음 (핵심 요소임)**
> - ✅ “Global SLAM = offline” → **맞음 (offline SLAM의 주 처리 요소)**

하지만 실제로:
- Online SLAM에서도 Global SLAM이 **실시간으로 background 최적화**로 작동하고 있고,
- Offline SLAM에서는 전체 pose graph를 한번에 최적화하는 **정적 처리**를 의미해요.

---

📌 추가로 알고 싶으신 게 있다면:
- `cartographer_offline_node` 구성법
- `rosbag_validate`로 offline mapping 예시
- online → offline 비교 실험 예

<br>
<br>
<br>
<br>
<br>
<br>


시스템 구성 기반으로로 각 용어를 **Cartographer 기반 AMR 운영 흐름**에 맞게 정리해드릴게요.  
지금처럼:

> 📌 **"1대의 AMR이 Cartographer로 맵핑한 후, 저장된 맵으로 pure localization만 사용"**

이라는 조건에 **정확하게 대응되는 형태로 설명**드릴게요.

---

# 📘 용어 정리 (당신의 AMR 운영 흐름 기준)

---

## ✅ 1. **Local SLAM (Front-End)**

**정의:**  
센서 데이터가 실시간으로 들어올 때, **현재 로봇의 위치를 빠르게 추정**하고, **submap을 생성**하는 단계.

**시스템 구성:**  
- **맵핑 시점에만 사용됨**
- `/scan`, `/imu`, `/odometry/filtered`를 기반으로 실시간 위치 추정
- submap 생성에 사용

---

## ✅ 2. **Global SLAM (Back-End)**

**정의:**  
여러 pose들을 연결한 **pose graph**를 기반으로, 전체 맵과 로봇의 경로를 **최적화**하는 과정.  
Loop closure 등을 수행함.

**시스템 구성:**  
- 맵핑 도중에 백그라운드로 수행됨  
- 맵 저장 전에 **전체 맵의 일관성**을 확보해 줌  
- **pure localization 시에는 사용되지 않음**

---

## ✅ 3. **Online SLAM**

**정의:**  
로봇이 움직이며 **실시간으로 SLAM을 수행**하는 것. Local SLAM + 일부 Global SLAM이 함께 작동.

**시스템 구성:**  
- **맵핑할 때만 해당**  
- mapping 중 실시간 위치 추정 + 맵 생성 + 백그라운드 pose graph 최적화

---

## ✅ 4. **Offline SLAM**

**정의:**  
이미 수집된 센서 데이터를 기반으로, **나중에 loop closure 및 pose graph 최적화를 수행**하여 정확한 맵을 생성하는 것.

**시스템 구성:**  
- 사용하지 않음  
- 사용하고 싶다면 `ros2 bag`으로 데이터를 저장 후 `cartographer_offline_node`로 처리 가능

---

## ✅ 5. **Pure Localization**

**정의:**  
기존에 생성된 맵을 기반으로, **로봇의 현재 위치만 실시간 추정**하는 모드. 새로운 submap이나 graph를 만들지 않음.

**시스템 구성:**  
- 주행 시에는 **항상 이 모드로 작동**  
- `.pbstream`을 로딩하고, 현재 scan을 맵과 매칭하여 위치 추정
- `.lua` 설정에서 `pure_localization = true`

---

## ✅ 6. **Pose Graph**

**정의:**  
로봇의 여러 위치(pose)들과 그 사이의 관계(constraints)를 그래프로 표현한 것.

구성:
- **노드 (Node):** 각 시점의 로봇 위치
- **엣지 (Constraint):** 노드들 간의 상대적 위치 관계 (scan matching, odometry 등)

**시스템 구성:**  
- 맵핑 시에는 생성되고, 최적화되어 `.pbstream`에 저장  
- 주행 시에는 **읽기 전용** (수정 X)

---

## ✅ 7. **Pose Graph Optimization**

**정의:**  
모든 노드와 엣지 관계를 기반으로, 전체 pose들을 **전역적으로 일관되게 정렬**하는 작업.

**시스템 구성:**  
- 맵핑 중 백그라운드로 수행됨  
- loop closure 감지 후, 전체 궤적을 재정렬  
- Ceres Solver를 사용함

---

## ✅ 8. **Ceres Solver**

**정의:**  
Google의 고성능 최적화 라이브러리. Pose Graph 최적화 시 사용.

최적화 문제 예:
```math
Minimize ∑ (오차²)
```
- 각 constraint의 오차를 줄이기 위한 비선형 최적화

**시스템 구성:**  
- 맵핑 중에 loop closure 이후 pose들을 재정렬할 때 사용됨  
- pure localization 시에는 사용되지 않음

---

## ✅ 9. **Scan Matching Score**

**정의:**  
현재 LIDAR scan이 기존 맵(submap)과 얼마나 잘 일치하는지를 나타내는 점수 (높을수록 잘 맞음)

**시스템 구성:**  
- pure localization 중 **로봇 위치를 추정할 때 핵심적으로 사용됨**
- scan matching score가 낮으면 localization이 불안정할 수 있음

---

## ✅ 10. **Ceres Scan Matcher**

**정의:**  
Scan Matching의 고정밀 단계. 현재 scan과 submap을 비교해 최적 pose를 찾음.  
(Real-Time Correlative Scan Matching 이후 정밀 보정)

**시스템 구성:**  
- mapping 시, 그리고 pure localization 시 모두 사용됨  
- 특히 로봇이 정지 후 이동 재개할 때 위치 추정 정확도에 기여

---

## ✅ 11. **Trajectory**

**정의:**  
로봇이 움직이며 남긴 pose의 연속. Cartographer에서는 각 trajectory마다 ID가 부여됨.

**시스템 구성:**  
- 맵핑 시에는 trajectory 0 하나가 생성됨  
- pure localization 시에는 이 trajectory는 **"frozen"** 상태로, 위치 추정만 참고됨

---

## ✅ 12. **Submap**

**정의:**  
로봇이 일정 거리 또는 시간 동안 움직이며 생성한 **로컬 맵 조각**

**시스템 구성:**  
- 맵핑 시 계속 생성되고 `.pbstream`에 저장됨  
- pure localization 시에는 새로 생성되지 않음. 기존 submap과 scan만 비교

---

## ✅ 13. **.pbstream**

**정의:**  
Cartographer가 만든 binary 파일. 전체 pose graph, submap, sensor data 등을 포함

**시스템 구성:**  
- mapping 후 저장하고  
- navigation 시 pure localization 모드로 로딩해서 사용

---

# ✅ 최종 요약 (운영 흐름 중심)

| 시점 | 작동 모드 | 작동 내용 | 사용된 구성 요소 |
|------|-----------|-----------|------------------|
| **Mapping 중** | Online SLAM | 실시간 위치 추정 + 맵 생성 + pose graph 최적화 | Local SLAM, Global SLAM, Pose Graph, Ceres Solver, Scan Matching |
| **Mapping 후** | 저장 | `.pbstream` 생성 | submap, trajectory, constraints 저장 |
| **주행 중** | Pure Localization | 기존 맵으로 위치 추정만 수행 | Ceres Scan Matcher, Scan Matching Score, submap 사용 |

---

필요하시면 이 흐름을 도식화한 PDF나 시각 자료도 만들어드릴 수 있어요.  
다음은 어떤 걸 더 깊이 알아보고 싶으세요?

- pure localization을 위한 `initialpose` 자동 주입?
- scan matching 튜닝 파라미터 설명?
- loop closure가 잘 안 되는 경우 대처법?  
- `pbstream`에서 submap 시각화 도구 만들기?

<br>
<br>
<br>
<br>
<br>


📘 **Cartographer SLAM 용어 정리 (AMR 운영 흐름 중심)**

---

✅ **1. Local SLAM (Front-End)**
- **정의:** 센서 데이터가 실시간으로 들어올 때, 현재 로봇의 위치를 빠르게 추정하고 submap을 생성하는 단계.
- **쉽게 말하면:** "지금 내가 어디에 있는지 바로바로 계산하기"
- **시스템 구성:** 맵핑할 때만 사용. `/scan`, `/imu`, `/odometry/filtered`를 통해 로봇 위치를 추정하고 submap 생성.

✅ **2. Global SLAM (Back-End)**
- **정의:** 여러 pose들을 연결한 pose graph를 기반으로 전체 맵과 경로를 최적화하는 과정. loop closure도 수행.
- **쉽게 말하면:** "지나온 길을 되짚어보며 경로를 정리하기"
- **시스템 구성:** 맵핑 중 백그라운드에서 작동. pure localization 시에는 사용되지 않음.

✅ **3. Online SLAM**
- **정의:** 로봇이 움직이며 실시간으로 SLAM을 수행하는 것.
- **쉽게 말하면:** "지도 만들면서 동시에 위치 추적하는 실시간 모드"
- **시스템 구성:** 맵핑할 때만 해당. Local SLAM + 일부 Global SLAM 함께 작동.

✅ **4. Offline SLAM**
- **정의:** 기록된 센서 데이터를 기반으로 나중에 맵과 경로를 최적화하는 후처리 방식.
- **쉽게 말하면:** "기록해둔 주행 데이터를 나중에 돌려보며 정밀하게 맵 생성"
- **시스템 구성:** 사용하지 않음. 필요 시 rosbag 기록 + `cartographer_offline_node` 사용 가능.

✅ **5. Pure Localization**
- **정의:** 기존에 만든 맵을 기반으로 현재 위치만 실시간으로 추정하는 모드.
- **쉽게 말하면:** "이미 있는 지도를 보며 내 위치만 찾기"
- **시스템 구성:** 주행 시 항상 이 모드. `.pbstream`을 불러와 현재 scan과 비교하여 위치 추정.

✅ **6. Pose Graph**
- **정의:** 로봇의 위치(pose)들과 그 사이 관계(constraint)를 연결한 그래프 구조.
- **쉽게 말하면:** "로봇이 지나온 경로와 관계를 선으로 연결한 지도"
- **시스템 구성:** 맵핑 중 생성되고 최적화됨. 주행 시에는 읽기 전용.

✅ **7. Pose Graph Optimization**
- **정의:** Pose Graph 상의 노드들을 전역적으로 정렬해서 정확한 맵 생성.
- **쉽게 말하면:** "전체 경로를 정렬해서 지도를 바로잡기"
- **시스템 구성:** loop closure 발생 후 백그라운드에서 실행. Ceres Solver 사용.

✅ **8. Ceres Solver**
- **정의:** Google의 고성능 비선형 최적화 도구로 pose graph 정렬에 사용.
- **쉽게 말하면:** "위치 오차를 수학적으로 줄이는 계산기"
- **시스템 구성:** 맵핑 중 pose 정렬 시 사용됨. 주행 중에는 사용되지 않음.

✅ **9. Scan Matching Score**
- **정의:** 현재 scan과 기존 맵이 얼마나 잘 맞는지를 나타내는 점수.
- **쉽게 말하면:** "지금 보는 풍경이 기존 지도와 얼마나 비슷한가"
- **시스템 구성:** pure localization 중 로봇 위치 정확도를 판단하는 핵심 지표.

✅ **10. Ceres Scan Matcher**
- **정의:** 고정밀 scan matcher로, scan과 submap을 비교해 최적 위치를 계산.
- **쉽게 말하면:** "정밀하게 현재 위치를 찾는 계산기"
- **시스템 구성:** 맵핑 시와 주행 시 모두 사용됨. 정밀 위치 추정에 도움.

✅ **11. Trajectory**
- **정의:** 로봇이 이동하며 기록된 pose의 연속.
- **쉽게 말하면:** "로봇의 발자국 모음"
- **시스템 구성:** 맵핑 중 trajectory 0 생성. pure localization에서는 이 trajectory는 고정 상태 (frozen).

✅ **12. Submap**
- **정의:** 일정 거리마다 생성되는 로컬 지도 조각.
- **쉽게 말하면:** "작게 나눈 지도 조각들"
- **시스템 구성:** 맵핑 중 지속적으로 생성되고 `.pbstream`에 저장됨. 주행 중에는 기존 submap만 참조.

✅ **13. .pbstream**
- **정의:** Cartographer가 만든 바이너리 파일. 맵, pose graph, 센서 정보 등이 포함됨.
- **쉽게 말하면:** "맵과 로봇 경로가 모두 저장된 압축파일"
- **시스템 구성:** 맵핑 후 저장. pure localization 모드로 주행 시 로딩함.


<br>
<br>
<br>
<br>
<br>


![image](https://github.com/user-attachments/assets/6ffd48e6-b14c-4300-a797-3bdbe9c5a612)

<br>



 "각 용어의 작동 방식 흐름도 (flowchart)"의 시각화입니다. 아래는 설명과 함께 흐름도 구조를 정리한 것입니다:

---

### 🧭 **Cartographer SLAM 운영 흐름도 (AMR 기준)**

```plaintext
[Mapping 시작]
      |
      v
[센서 입력 (scan, imu, odom)]
      |
      v
 ┌──────────────────────┐
 │   Local SLAM (Front-End)   │ ◀──────────────┐
 └──────────────────────┘                      │
      |                                        │
      v                                        │
 ┌──────────────────────┐                      │
 │ Submap 생성                     │                      │
 └──────────────────────┘                      │
      |                                        │
      v                                        │
 ┌─────────────────────────────┐               │
 │ Pose Graph에 Node/Edge 추가      │               │
 └─────────────────────────────┘               │
      |                                        │
      v                                        │
 ┌──────────────────────────────┐              │
 │ Pose Graph Optimization (Back-End) │◀──────┘ (Loop Closure 발생 시)
 └──────────────────────────────┘
      |
      v
[Ceres Solver로 최적화 수행]
      |
      v
[최종 Map 저장 (.pbstream)]

      ▼

[Navigation / 주행 시점]
      |
      v
[맵 불러오기 (.pbstream)]
      |
      v
[pure localization = true]
      |
      v
[Scan + Submap → 위치 추정]
      |
      v
[Nav2 → 경로 계획 및 로컬 플래닝]
```

---

### 🧩 각 단계에서의 역할 요약

| 단계 | 설명 | 사용된 개념 |
|------|------|--------------|
| Mapping | 센서 기반 SLAM 수행 | Local SLAM, Global SLAM, Pose Graph, Ceres Solver |
| Optimization | 경로 최적화 | Pose Graph Optimization |
| 저장 | 모든 데이터 `.pbstream`에 저장 | Trajectory, Submap 포함 |
| 주행 시점 | 기존 맵 기반 실시간 위치 추정 | Pure Localization, Scan Matching Score, Ceres Scan Matcher |

---

필요하시면 이 ASCII 다이어그램을 **그래픽 이미지 (PNG, PDF)** 로도 만들어드릴 수 있어요.  

<br>
<br>
<br>
<br>
<br>
<br>
<br>


**Ceres Solver**와 **Ceres Scan Matcher**는 이름은 비슷하지만 **용도와 사용 맥락이 서로 다릅니다.**  
둘 다 Google의 [Ceres Solver 라이브러리](http://ceres-solver.org)를 기반으로 하지만, Cartographer 내부에서 **서로 다른 역할**을 합니다.

---

## ✅ 1. Ceres Solver

### ✔️ 정의:
- Google에서 만든 **비선형 최적화 라이브러리**
- Cartographer 내부의 **Pose Graph Optimization** 단계에서 사용됨
- 여러 pose와 constraint(제약 조건)를 기반으로, 전체 경로를 **전역적으로 최적화**함

### ✔️ 작동 위치:
- **Global SLAM (Back-End)** 영역
- Loop Closure가 감지되었을 때 전체 pose를 정렬하기 위해 사용

### ✔️ 예시:
로봇이 일자로 100m 주행하고 처음 위치로 되돌아왔을 때, 시작점과 끝점이 약간 어긋나 있다면:
- Ceres Solver가 **모든 노드들의 위치를 조금씩 조정**해서, 전체 경로가 자연스럽게 연결되도록 한다.

### ✔️ 핵심 개념:
- Pose Graph를 수학적으로 모델링하고,
- 오차 함수(Residuals)를 최소화하는 방식으로 위치를 최적화

---

## ✅ 2. Ceres Scan Matcher

### ✔️ 정의:
- Ceres Solver를 기반으로 만든 **정밀 Scan Matching 알고리즘**
- 현재 LIDAR scan과 기존 submap 간의 상대 위치를 계산할 때 사용됨
- 고속 스캔 매칭 이후, 더 정확한 위치 추정을 위해 보정하는 용도

### ✔️ 작동 위치:
- **Local SLAM (Front-End)** 에서 사용됨 (mapping & pure localization 모두)
- Real-Time Correlative Scan Matching (RTCSM) → coarse alignment
- **Ceres Scan Matcher** → fine alignment

### ✔️ 예시:
현재 scan을 submap과 비교해볼 때 대략적인 위치는 RTCSM이 계산하지만,  
좀 더 정확하게 위치를 미세 조정할 때 Ceres Scan Matcher가 사용됨.

---

## 📌 요약 비교표

| 항목 | Ceres Solver | Ceres Scan Matcher |
|------|--------------|--------------------|
| 용도 | 전체 pose graph 최적화 | 현재 scan의 pose 보정 |
| 위치 | Global SLAM (Back-End) | Local SLAM (Front-End) |
| 입력 | pose 간 constraint | scan + submap |
| 출력 | 전체 경로 보정된 pose | 현재 pose (정밀) |
| 사용 시점 | loop closure 후 최적화 | scan 입력 시마다 실시간 |
| 기반 라이브러리 | Ceres Solver | Ceres Solver |

---

## ✅ 정리

> 🔸 **Ceres Solver**는 Cartographer의 “두뇌” — 전체 맵을 정렬해줍니다.  
> 🔹 **Ceres Scan Matcher**는 Cartographer의 “현미경” — 현재 위치를 아주 정밀하게 찾아줍니다.

---

혹시 더 깊이 들어가고 싶은 부분이 있을까요?
- Ceres Scan Matcher 파라미터 설정 (`translation_weight`, `rotation_weight`)
- Ceres Solver가 최적화할 때 사용하는 residual 식
- RTCSM vs Ceres Scan Matcher 비교

<br>
<br>
<br>
<br>
<br>

![image](https://github.com/user-attachments/assets/de228c2f-0b2f-4e99-97c2-a2e37d5e3c7f)

<br>
<br>

해당 이미지는 Cartographer SLAM의 핵심 구조를 시각적으로 잘 정리한 **Technical Overview** 다이어그램입니다.  
이 다이어그램을 기반으로 각 모듈의 작동 원리를 **AMR에서의 실제 흐름**에 맞춰 상세하게 설명드릴게요.

---

## 🧭 전체 구조 요약

해당 그림은 Cartographer의 작동 과정을 다음 3개의 영역으로 나눠 설명합니다:

1. **Input Sensor Data** (입력 데이터)
2. **Local SLAM** (실시간 위치 추정 및 submap 생성)
3. **Global SLAM** (백그라운드에서 pose graph 최적화 수행)

---

## ✅ 1. Input Sensor Data

| 센서 종류 | 설명 |
|-----------|------|
| **Range Data** | LIDAR 또는 Point Cloud (`/scan`, `/points2`) |
| **Odometry Pose** | 바퀴 odometry or EKF 결과 (`/odom`) |
| **IMU Data** | 가속도, 각속도 (`/imu/data`) |
| **Fixed Frame Pose** | 보통 GPS 또는 초기 위치 지정 frame (보통은 사용 X) |

→ 이 데이터들은 **PoseExtrapolator** 모듈에 입력되어 시간 간격을 보정하고, 예측 위치 추정에 사용됩니다.

---

## ✅ 2. Local SLAM (실시간 SLAM)

### 🧩 주요 구성 요소 설명:

---

### ◾ **Voxel Filter / Adaptive Voxel Filter**
- LIDAR나 Point Cloud의 밀도를 줄여서 연산량을 줄임
- Adaptive Voxel Filter는 상황에 따라 더 정교한 필터링 수행

---

### ◾ **PoseExtrapolator**
- IMU + Odometry 데이터를 기반으로 현재 위치를 예측
- Scan Matching 이전 단계에서 초기 위치 추정값 제공

---

### ◾ **Scan Matching (Ceres Scan Matcher)**
- 예측 위치를 기반으로 실제 scan 데이터를 기존 submap과 비교하여 최적 위치 계산
- Ceres 기반의 고정밀 scan matcher
- 결과 → `PoseObservation`

---

### ◾ **Motion Filter**
- 로봇이 거의 움직이지 않거나 동일한 위치에 있을 경우, 계산 생략
- 너무 작은 움직임은 `Dropped` 처리 → 불필요한 submap 업데이트 방지

---

### ◾ **Submaps / Voxel Grid Update**
- 일정 거리마다 submap이라는 로컬 맵 조각을 생성
- 필터를 통과한 scan은 현재 submap에 삽입되어 누적됨
- 보통 동시에 2개의 submap이 활성화됨 (active submaps)

---

### ◾ **InsertionResult**
- scan이 submap에 삽입되면 그 시점의 정보(time, pose, range data 등)를 저장
- 이 정보는 이후 **Global SLAM**에서 pose graph를 구성할 때 사용됨

---

## ✅ 3. Global SLAM (백그라운드 최적화)

> 이 파트는 실시간이 아닌, 별도의 스레드로 작동합니다. 특히 loop closure나 trajectory 정렬을 담당합니다.

---

### ◾ **Compute Constraints**
- 노드(node)와 submap 사이의 관계(제약 조건)를 계산  
  - **INTRA**: 동일 submap 내의 제약 (일반 위치 관계)
  - **INTER**: loop closure 제약 (과거 submap과의 관계)

---

### ◾ **Sparse Pose Adjustment**
- pose graph 전체를 구성하고 최적화
- Ceres Solver를 이용해 pose 간 오차를 최소화하는 방향으로 경로 정렬

---

### ◾ **Extrapolate all poses added later**
- 이전 최적화 이후에 추가된 node들의 위치 보정

---

## 🔄 전체 흐름 요약

```plaintext
[센서 입력] → [Extrapolation + Filtering] 
→ [Scan Matching + Motion Filter] 
→ [Submap 삽입 (활성 상태)] 
→ [InsertionResult 저장]
→ [Global SLAM이 Constraints 계산 → Pose Graph Optimization 수행]
```

---

## 📍 당신의 AMR 시스템에 적용해 보면?

| 모듈 | 당신의 시스템 |
|------|---------------|
| IMU Data | `wit_imu_driver` + `imu_filter_madgwick` |
| Odometry | `robot_localization (EKF)` 결과 |
| Range Data | SICK nanoScan3의 `/scan` |
| Local SLAM | Mapping 시 작동, 주행 시에는 off |
| Global SLAM | Mapping 시 백그라운드로 작동, 주행 시에는 꺼짐 |
| Pure Localization | `.pbstream` 로딩 + scan과 submap만 비교하여 위치 추정 |

---

## ✅ 핵심 개념 연결 요약

| 개념 | 그림 상 위치 | 설명 |
|------|--------------|------|
| **Ceres Scan Matcher** | Local SLAM - Scan Matching | 실시간 위치 추정 |
| **Pose Graph** | Global SLAM | 모든 node/submap의 관계 |
| **Ceres Solver** | Sparse Pose Adjustment 내부 | pose graph 최적화 |
| **Submap** | Submaps + Voxel Grid Update | 로컬 맵 조각 |
| **InsertionResult** | Submap 삽입 결과 | 이후 global 최적화용 자료 |

---

필요하시면 이 그림을 기반으로 하는 **PDF 슬라이드**, 또는 각 모듈에 번호 붙여서 단계별 설명 자료도 만들어드릴 수 있어요.  
다음으로 설명해드릴까요?

- pure localization 시 위 구조에서 어떤 부분만 작동하는지?
- 각 박스별 내부 알고리즘 예시 (예: scan matching 수식)?
- Parameter tuning 포인트?


