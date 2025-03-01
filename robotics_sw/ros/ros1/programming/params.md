 **ROS1에서 파라미터를 관리할 때** `launch` 파일과 `params.yaml`을 언제 사용하는 게 더 좋은지에 대해 정리해볼게요.  

---

## 🚀 **1. launch 파일에서 파라미터 설정할 때**
🔹 **launch 파일에서 직접 파라미터를 설정하는 경우**는 주로 **런타임에서 변경 가능성이 있는 값**을 지정할 때 사용됩니다.

### ✅ **언제 launch 파일에서 설정하는 것이 좋은가?**
1. **테스트 또는 개발 환경에서 자주 변경하는 값**
   - 예: `simulation:=true` 같은 변수
   - 예: 특정 노드 실행 여부 (`use_lidar:=false`)
2. **간단한 파라미터 (1~2개 정도)**
   - 너무 많은 값을 `launch` 파일에서 설정하면 가독성이 떨어짐
3. **특정 실행 환경에 따라 동적으로 값을 설정할 때**
   - 예: `arg`를 사용해서 실행 시 입력을 받을 때  
   ```xml
   <launch>
       <arg name="robot_name" default="my_robot"/>
       <param name="robot_name" value="$(arg robot_name)"/>
   </launch>
   ```
4. **파일 없이 바로 실행해야 할 때**
   - `roslaunch` 명령어 하나만으로 실행 가능 (`rosparam load` 없이)

### 📌 **launch 파일에서 파라미터 설정 예시**
```xml
<launch>
    <!-- 정수형 파라미터 -->
    <param name="max_speed" value="1.0"/>
    
    <!-- 문자열 파라미터 -->
    <param name="robot_name" value="turtlebot"/>
    
    <!-- 동적으로 arg를 받는 경우 -->
    <arg name="use_sim" default="true"/>
    <param name="use_sim" value="$(arg use_sim)"/>
</launch>
```
📌 **장점**: 빠른 실행 가능, 특정 실행 환경(예: `sim_mode:=true`)에서 동적 변경 가능  
📌 **단점**: 파라미터가 많아지면 `launch` 파일이 지저분해짐

---

## 📂 **2. params.yaml 파일에서 파라미터 관리할 때**
🔹 **params.yaml을 사용하는 경우**는 주로 **구조적으로 관리할 필요가 있는 여러 개의 파라미터**를 설정할 때 적합합니다.

### ✅ **언제 params.yaml에서 설정하는 것이 좋은가?**
1. **파라미터 개수가 많을 때**
   - 예: PID 제어 파라미터, 센서 설정 값 등
2. **일관성 있는 설정이 필요할 때**
   - 다른 로봇에서도 같은 파라미터를 공유해야 할 때
3. **코드와 독립적으로 설정 파일만 수정해서 동작을 조정하고 싶을 때**
   - 개발/운영 환경에서 동일한 코드지만 설정만 다르게 적용 가능
4. **파라미터의 계층 구조가 필요한 경우**
   - 예: 카메라 관련 설정, 컨트롤러 관련 설정 등

### 📌 **params.yaml 예시**
```yaml
robot:
  max_speed: 1.0
  min_speed: 0.2

sensors:
  lidar:
    resolution: 0.05
    range: 10.0
  camera:
    fps: 30
    resolution: [1920, 1080]
```

### 📌 **launch 파일에서 params.yaml을 불러오는 방법**
```xml
<launch>
    <rosparam file="$(find my_robot)/config/params.yaml" command="load"/>
</launch>
```
📌 **장점**: 파라미터가 많을 때 깔끔하게 관리 가능, 유지보수 용이  
📌 **단점**: `roslaunch` 실행 전에 `rosparam load` 해야 적용됨 (자동으로 로드하려면 `launch` 파일에서 설정 필요)

---

## 🔥 **결론: launch vs. params.yaml**
| 비교 항목 | launch 파일 (`<param>`) | params.yaml |
|----------|-----------------|------------------|
| **주 사용 목적** | 빠르게 실행 시 설정 변경 | 대량의 파라미터 관리 |
| **적합한 상황** | 몇 개 안 되는 단순한 값, 실행 환경 변경 | 여러 개의 복잡한 설정, 유지보수 필요 |
| **가독성** | 파라미터가 많아지면 관리 어려움 | YAML 구조 덕분에 가독성이 좋음 |
| **변경 용이성** | 실행 중에 수정 가능 | 설정 파일만 수정하면 됨 |
| **적용 방법** | `<param name="key" value="val"/>` | `<rosparam file="params.yaml" command="load"/>` |

### **📌 실무에서 어떻게 사용하면 좋은가?**
✅ **launch 파일에는 동적으로 변경할 가능성이 있는 파라미터만 넣기**  
✅ **params.yaml에는 복잡한 설정값(예: PID 값, 센서 설정 등) 저장하기**  
✅ **launch 파일에서 params.yaml을 불러와서 사용하기** (혼합 사용 가능)

이렇게 하면 **유지보수도 쉽고, 실행 시 변경도 편리**하게 할 수 있어요! 🚀


<br>
<br>
<br>
<br>


노드가 **실행 중**인 상태에서 파라미터를 업데이트하고 싶다면 **launch 파일이나 params.yaml이 아니라 `rosparam set`을 사용해야 합니다.**  

하지만 **launch 파일과 params.yaml 중에서 더 적합한 선택지를 고민하는 경우**, `params.yaml`보다는 **launch 파일이 더 유연**할 수 있습니다.  

---

## 🚀 **실행 중 파라미터 업데이트 방법**
ROS1에서는 **파라미터 서버**를 사용하여 실행 중인 노드의 파라미터를 변경할 수 있습니다.

### ✅ **방법 1: `rosparam set` 명령어 사용 (가장 즉각적인 방법)**
만약 특정 파라미터 값을 실행 중에 바꾸고 싶다면, 아래처럼 `rosparam set`을 사용할 수 있습니다.
```bash
rosparam set /robot/max_speed 2.0
```
👉 **즉시 파라미터가 변경되지만, 현재 실행 중인 노드가 이 값을 다시 읽지 않으면 적용되지 않을 수도 있음!**  
👉 `ros::NodeHandle::getParam()`은 한 번만 값을 읽기 때문에, **재시작하지 않으면 반영되지 않을 수 있음.**  
👉 이를 해결하려면 노드가 **주기적으로 `getParam()`을 호출하도록 구현**해야 함.

예제 코드 (C++):
```cpp
ros::NodeHandle nh;
double max_speed;
while (ros::ok()) {
    nh.getParam("/robot/max_speed", max_speed);
    ROS_INFO("Updated max speed: %f", max_speed);
    ros::Duration(1.0).sleep();
}
```
---

### ✅ **방법 2: Dynamic Reconfigure 사용 (추천)**
`dynamic_reconfigure` 패키지를 사용하면 **GUI 또는 명령어로 실시간으로 파라미터를 조정할 수 있음.**  
이를 사용하면 노드를 재시작하지 않고도 설정을 즉시 반영할 수 있음.

#### **설치**
```bash
sudo apt-get install ros-<ros-version>-dynamic-reconfigure
```

#### **C++ 코드 예제**
```cpp
#include <dynamic_reconfigure/server.h>
#include <my_robot/MyConfigConfig.h>

void callback(my_robot::MyConfigConfig &config, uint32_t level) {
    ROS_INFO("Reconfigure Request: %f", config.max_speed);
}

int main(int argc, char **argv) {
    ros::init(argc, argv, "dynamic_reconfigure_node");
    ros::NodeHandle nh;

    dynamic_reconfigure::Server<my_robot::MyConfigConfig> server;
    dynamic_reconfigure::Server<my_robot::MyConfigConfig>::CallbackType f;

    f = boost::bind(&callback, _1, _2);
    server.setCallback(f);

    ros::spin();
    return 0;
}
```
📌 **장점**: `rqt_reconfigure` GUI를 통해 실시간으로 값 변경 가능  
📌 **단점**: 추가 패키지 필요, 구현해야 함

#### **실행 방법**
```bash
rosrun rqt_reconfigure rqt_reconfigure
```
→ GUI에서 실시간으로 값 조정 가능 🚀

---

## 📌 **결론: launch vs. params.yaml 중 어떤 게 더 나은가?**
| 비교 항목 | launch 파일 (`<param>`) | params.yaml (`rosparam load`) |
|----------|----------------|------------------|
| **적합한 경우** | 런타임 중 값 변경 가능성이 있을 때 | 한 번 로드 후 변경할 일이 거의 없을 때 |
| **노드 실행 중 변경 가능?** | 직접 수정 불가 (`rosparam set` 필요) | 직접 수정 불가 (`rosparam set` 필요) |
| **실행 중 변경 적용 방법** | `rosparam set` 또는 `dynamic_reconfigure` 사용 | `rosparam set` 사용 |
| **가독성 및 유지보수성** | 적은 수의 파라미터일 경우 유용 | 복잡한 설정값 관리에 적합 |

---

## 🔥 **추천 전략**
- **launch 파일**에서 `arg`를 사용해 쉽게 변경할 수 있도록 설정  
- **params.yaml**은 주로 **고정된 설정 값**(예: 센서 파라미터, PID 값 등)에 사용  
- **실행 중 값 변경이 필요하면 `rosparam set` 또는 `dynamic_reconfigure` 사용**

즉, **런타임 중 값을 바꿀 일이 많다면 `dynamic_reconfigure`를 적극 활용**하고,  
단순한 변경은 `rosparam set`으로도 충분합니다! 🚀

<br>
<br>
<br>
<br>
네! **launch 파일(`.launch`)과 params.yaml(`.yaml`)에서 변경된 파라미터는 `catkin_make`를 다시 실행하지 않아도 적용됩니다.** 하지만 적용 방식이 조금 다릅니다.

---

## 🚀 **1. catkin_make 없이 즉시 반영되는 경우**
### ✅ **Launch 파일 (`.launch`) 변경**
- **launch 파일 자체를 수정하는 경우**, `roslaunch`를 다시 실행하면 적용됩니다.
- 실행 중인 노드에는 영향을 주지 않지만, **노드를 다시 시작하면 적용**됩니다.
- 즉, **launch 파일을 수정한 후에는 `roslaunch`를 재실행**해야 합니다.

#### 📌 예제 (launch 파일 수정 후 바로 적용 가능)
```xml
<launch>
    <param name="robot_speed" value="1.5"/>
</launch>
```
🔹 위 파일에서 `robot_speed` 값을 2.0으로 변경 후, 다시 `roslaunch` 실행하면 반영됨.

```bash
roslaunch my_robot robot_launch.launch
```
✅ **catkin_make 필요 없음!**  
✅ 하지만 **노드를 다시 실행해야 변경 사항 적용됨**.

---

### ✅ **YAML 파일 (`.yaml`) 변경**
- YAML 파일을 직접 수정하면 즉시 반영되지 않지만, **수동으로 다시 로드하면 재적용 가능**.
- `rosparam load` 명령어를 사용하면 실행 중에도 변경 가능.

#### 📌 예제 (params.yaml)
```yaml
robot:
  speed: 1.5
  sensor_range: 10.0
```
🔹 `sensor_range`를 15.0으로 수정 후, 아래 명령어 실행:
```bash
rosparam load ~/catkin_ws/src/my_robot/config/params.yaml
```
✅ **catkin_make 필요 없음!**  
✅ **노드가 `ros::NodeHandle::getParam()`을 주기적으로 호출하면 즉시 반영**  
❌ 하지만, 일부 노드는 파라미터를 한 번만 읽고 계속 실행되므로 반영되지 않을 수도 있음 → 이 경우 노드 재시작 필요

---

## ❌ **2. catkin_make가 필요한 경우**
**다음과 같은 경우는 catkin_make를 다시 해야 합니다.**
1. **C++ 코드에서 파라미터를 하드코딩한 경우**
   ```cpp
   double max_speed = 1.5;  // 고정된 값
   ```
   → 코드 변경 후 `catkin_make` 필요

2. **CMakeLists.txt 수정 (새 노드 추가 등)**
   - `add_executable()`을 변경하거나 새 노드를 추가한 경우

3. **새 메시지(`.msg`), 서비스(`.srv`), 액션(`.action`) 추가**
   - `catkin_make`를 통해 빌드하지 않으면 새로운 메시지 타입을 인식할 수 없음

---

## 🔥 **결론: catkin_make 없이 반영 가능한 경우**
| 변경 내용 | catkin_make 필요? | 적용 방법 |
|-----------|-----------------|----------------------|
| **launch 파일 수정** | ❌ 필요 없음 | `roslaunch` 다시 실행 |
| **params.yaml 수정** | ❌ 필요 없음 | `rosparam load` 실행 |
| **C++ 코드에서 하드코딩 값 변경** | ✅ 필요함 | `catkin_make` 후 노드 재실행 |
| **새로운 메시지(.msg) 추가** | ✅ 필요함 | `catkin_make` 후 `source devel/setup.bash` 실행 |
| **새로운 노드 추가** | ✅ 필요함 | `catkin_make` 후 실행 |

### **📌 실무에서 적용 전략**
- **Launch & YAML 파일 수정** → `catkin_make` 없이 바로 적용 가능  
- **실행 중 업데이트** → `rosparam set` 또는 `rosparam load` 활용  
- **C++ 코드 변경** → `catkin_make` 후 재실행 필요

즉, **launch나 yaml 파일에서 설정한 값은 catkin_make 없이도 변경 가능하지만, 노드를 재시작해야 반영**됩니다! 🚀



<br>
<br>
<br>
<br>

네, 맞습니다! **params.yaml에서 관리되는 파라미터가 launch 파일에서 관리되는 파라미터보다 더 자유도가 높습니다.** 🚀  
그 이유를 정리해보면 다음과 같습니다.  

---

## 🔥 **1. params.yaml이 launch 파일보다 더 자유로운 이유**  
### ✅ **(1) 실행 중 업데이트 가능 (`rosparam load`)**
- params.yaml 파일은 실행 중에도 `rosparam load` 명령어로 다시 로드할 수 있음.
- launch 파일의 `<param>` 태그는 노드 실행 전에만 로드되므로, 실행 중 업데이트가 어렵다.

📌 **params.yaml 업데이트 예제**
```bash
rosparam load ~/catkin_ws/src/my_robot/config/params.yaml
```
✅ **실행 중에도 적용 가능!**  
✅ **노드를 재시작하지 않아도 반영될 가능성이 있음** (단, 노드가 `getParam()`을 주기적으로 호출해야 함)  
❌ **launch 파일은 재실행해야 적용됨**  

---

### ✅ **(2) 파라미터 계층 구조 지원**
- YAML 파일은 계층적 구조를 가지므로, 그룹화하여 관리 가능.
- launch 파일의 `<param>` 태그는 단순한 `key-value` 형태만 지원.

📌 **params.yaml 예제 (계층 구조)**
```yaml
robot:
  max_speed: 1.5
  min_speed: 0.2

sensors:
  lidar:
    resolution: 0.05
    range: 10.0
  camera:
    fps: 30
    resolution: [1920, 1080]
```
✅ **같은 카테고리끼리 그룹화 가능 (ex. robot, sensors)**  
✅ **여러 노드에서 공통 설정을 쉽게 불러올 수 있음**  

📌 **launch 파일에서 같은 값 설정하면? (가독성 떨어짐)**
```xml
<param name="robot/max_speed" value="1.5"/>
<param name="robot/min_speed" value="0.2"/>
<param name="sensors/lidar/resolution" value="0.05"/>
<param name="sensors/lidar/range" value="10.0"/>
```
❌ **일일이 하나씩 지정해야 해서 불편함**  
❌ **파라미터가 많아지면 launch 파일이 너무 길어짐**  

---

### ✅ **(3) 하나의 params.yaml을 여러 개의 launch 파일에서 공유 가능**
- YAML 파일을 하나 만들어 놓으면 여러 launch 파일에서 불러올 수 있음.
- launch 파일에 직접 `<param>`을 사용하면, 각 launch 파일마다 동일한 파라미터를 반복적으로 설정해야 함.

📌 **params.yaml 한 번 작성 후 여러 launch 파일에서 사용 가능**
```xml
<rosparam file="$(find my_robot)/config/params.yaml" command="load"/>
```
✅ **다른 launch 파일에서도 같은 params.yaml을 사용 가능!**  
✅ **파라미터가 많아질수록 YAML 관리가 더 편리함**  

---

## 🔄 **2. launch 파일이 더 유리한 경우도 있음**
하지만, launch 파일이 더 유리한 상황도 있어요.

### ✅ **(1) 실행할 때마다 바뀌는 동적 값**
- launch 파일에서 `<arg>`를 활용하면 실행할 때마다 다른 값을 넣을 수 있음.

📌 **launch 파일에서 `arg` 활용 예제**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>
    <param name="robot_name" value="$(arg robot_name)"/>
</launch>
```
✅ **실행할 때 값 변경 가능!**
```bash
roslaunch my_robot robot_launch.launch robot_name:=my_robot1
```
❌ **params.yaml은 실행 전에 미리 설정해야 해서 동적 변경이 어려움**  

---

### ✅ **(2) 파라미터가 아주 적을 때**
- 간단한 파라미터는 launch 파일에서 `<param>`으로 바로 설정하는 게 더 직관적일 수도 있음.
- 예를 들어, `simulation_mode:=true` 같은 간단한 설정.

📌 **launch 파일에서 간단한 설정**
```xml
<launch>
    <param name="simulation_mode" value="true"/>
</launch>
```
✅ **YAML 파일 없이 간단한 설정을 추가할 때 유용함**  

---

## 📌 **결론: params.yaml이 더 자유도가 높은 이유**
| 비교 항목 | launch 파일 (`<param>`) | params.yaml (`rosparam load`) |
|----------|----------------|------------------|
| **실행 중 변경 가능?** | ❌ 재실행해야 적용됨 | ✅ `rosparam load`로 실행 중 업데이트 가능 |
| **계층 구조 지원?** | ❌ 불가능 | ✅ YAML 구조 지원 (가독성↑) |
| **여러 launch 파일에서 공유 가능?** | ❌ launch 파일마다 중복 설정 필요 | ✅ params.yaml을 한 번 작성해서 여러 개의 launch에서 사용 가능 |
| **동적 값 설정 (`arg` 사용)?** | ✅ 가능 (`roslaunch` 실행 시 변경 가능) | ❌ 실행 전에 미리 정의해야 함 |
| **간단한 설정에 적합?** | ✅ 예 (1~2개 정도) | ❌ YAML 파일을 만들 필요 없음 |

### 🚀 **최적의 전략**
- **동적으로 변경 가능해야 한다면 → YAML (`rosparam load`) 사용**
- **값이 실행할 때마다 바뀌어야 한다면 → launch 파일에서 `arg` 활용**
- **파라미터가 많고 계층적으로 관리해야 한다면 → YAML 사용**
- **단순한 설정이라면 → launch 파일에서 `<param>` 직접 사용**

즉, params.yaml을 활용하면 **더 유연한 파라미터 관리가 가능하고, 실행 중 업데이트도 더 쉽게 할 수 있기 때문에 자유도가 더 높습니다!** 🚀


<br>
<br>
<br>
<br>
## 🚀 **ROS1 `<arg>` 문법 및 활용법**
`<arg>`는 **ROS launch 파일에서 실행 시 동적으로 값을 전달할 수 있는 기능**입니다.  
즉, 특정 값(예: `robot_name`)을 미리 **고정하지 않고**, launch 파일 실행 시 결정할 수 있도록 하는 기능입니다.

---

## 🔹 **1. `<arg>` 기본 문법**
```xml
<arg name="변수명" default="기본값"/>
```
- `name`: 변수의 이름
- `default`: 기본값 (생략 가능, 기본값이 없으면 실행 시 반드시 입력해야 함)

📌 **기본 사용 예제**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>
    <param name="robot_name" value="$(arg robot_name)"/>
</launch>
```
- 실행 시 **아무 값도 주지 않으면** 기본값 `"turtlebot"`이 적용됨.
- 실행할 때 `robot_name` 값을 변경 가능!

---

## 🔹 **2. `<arg>`를 활용한 실행 방법**
### ✅ **(1) 기본값 사용 (값을 전달하지 않은 경우)**
```bash
roslaunch my_robot robot_launch.launch
```
✅ 기본값 `"turtlebot"`이 적용됨.

### ✅ **(2) 실행할 때 값 전달 (`:=` 사용)**
```bash
roslaunch my_robot robot_launch.launch robot_name:=my_robot1
```
✅ `"robot_name"`이 `"my_robot1"`로 설정됨.

---

## 🔹 **3. `<arg>`와 `<param>` 함께 사용**
`<arg>`를 이용하면 **동적으로 설정된 값을 ROS 파라미터 서버에 등록할 수 있음.**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>
    <param name="robot_name" value="$(arg robot_name)"/>
</launch>
```
- 실행 시 전달한 값이 `/robot_name` 파라미터로 등록됨.
- `rosparam get /robot_name`으로 확인 가능.

📌 **확인 방법**
```bash
roslaunch my_robot robot_launch.launch robot_name:=my_robot1
rosparam get /robot_name
```
출력:
```
my_robot1
```

---

## 🔹 **4. `<arg>`를 여러 개 활용하는 예제**
💡 **로봇 이름과 속도를 동적으로 설정**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>
    <arg name="max_speed" default="1.5"/>

    <param name="robot_name" value="$(arg robot_name)"/>
    <param name="max_speed" value="$(arg max_speed)"/>
</launch>
```
**실행 방법**
```bash
roslaunch my_robot robot_launch.launch robot_name:=my_robot2 max_speed:=2.0
```
**파라미터 확인**
```bash
rosparam get /robot_name
rosparam get /max_speed
```
**출력 결과**
```
my_robot2
2.0
```

---

## 🔹 **5. `<arg>`를 다른 태그와 함께 활용**
### ✅ **(1) `<group>`과 함께 사용 (네임스페이스 적용)**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>

    <group ns="$(arg robot_name)">
        <param name="max_speed" value="1.5"/>
    </group>
</launch>
```
**실행 결과 (`robot_name:=robot1` 일 때)**
```bash
roslaunch my_robot robot_launch.launch robot_name:=robot1
rosparam list
```
출력:
```
/robot1/max_speed
```
✅ **네임스페이스가 자동으로 설정됨!**

---

### ✅ **(2) `<include>`와 함께 사용 (다른 launch 파일에 전달)**
```xml
<launch>
    <arg name="robot_name" default="turtlebot"/>
    <include file="$(find my_robot)/launch/robot_control.launch">
        <arg name="robot_name" value="$(arg robot_name)"/>
    </include>
</launch>
```
- 다른 launch 파일(`robot_control.launch`)을 실행할 때 **같은 값을 전달**할 수 있음.

---

## 🔥 **6. `<arg>` vs. `<param>` 차이점**
| 비교 항목 | `<arg>` (`arg`) | `<param>` (`param`) |
|----------|----------------|----------------|
| **목적** | 실행 시 동적 값 설정 | ROS 파라미터 서버에 저장 |
| **값 변경 가능?** | 실행할 때 변경 가능 | 실행 중 `rosparam set`으로 변경 가능 |
| **기본값 지원?** | `default` 속성으로 지원 | 없음 (직접 설정해야 함) |
| **네임스페이스 적용?** | `<group ns="$(arg 값)">` 사용 가능 | 직접 이름을 지정해야 함 |

📌 **결론**
- `<arg>`: **launch 실행 시 값 변경이 필요할 때**
- `<param>`: **ROS 파라미터 서버에 저장해야 할 때**

🚀 **즉, `<arg>`는 launch 파일에서만 활용되고, `<param>`은 ROS 파라미터 서버에서 활용됨!**




<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
