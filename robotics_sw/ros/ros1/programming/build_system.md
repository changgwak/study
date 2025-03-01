### 🔥 **ROS1의 `CMakeLists.txt`에서 `add_executable()` 및 `target_link_libraries()` 문법 설명**

---

### **1️⃣ `add_executable()`**
```cmake
add_executable(robot_node src/main.cpp src/robot_controller.cpp)
```
📌 **설명:**  
- `robot_node`: 빌드할 실행 파일의 이름 (즉, ROS 노드의 실행 파일 이름)  
- `src/main.cpp src/robot_controller.cpp`: `robot_node`를 만들 때 필요한 소스 코드 파일 목록  

💡 **의미:**  
이 명령어는 **`src/main.cpp`와 `src/robot_controller.cpp`를 컴파일하여 `robot_node` 실행 파일을 생성**한다.  
이제 `catkin_make`를 실행하면 `robot_node`라는 실행 가능한 바이너리가 `devel/lib/<패키지명>/robot_node` 경로에 생성됨.

📌 **예제**  
만약 추가로 `robot_utils.cpp`라는 파일을 포함하려면?
```cmake
add_executable(robot_node src/main.cpp src/robot_controller.cpp src/robot_utils.cpp)
```

---

### **2️⃣ `target_link_libraries()`**
```cmake
target_link_libraries(robot_node ${catkin_LIBRARIES})
```
📌 **설명:**  
- `robot_node`: **위에서 `add_executable()`로 만든 실행 파일 이름**
- `${catkin_LIBRARIES}`: **catkin 패키지의 필요한 라이브러리들을 자동으로 연결**

💡 **의미:**  
이 명령어는 `robot_node` 실행 파일을 만들 때, **catkin에서 제공하는 ROS 관련 라이브러리와 자동으로 링크하도록 설정**한다.  
즉, ROS API(`ros::NodeHandle`, `ros::Publisher`, `ros::Subscriber` 등)를 사용할 수 있도록 필요한 라이브러리를 포함시켜준다.

📌 **만약 추가적인 라이브러리를 포함해야 한다면?**  
예를 들어, OpenCV 라이브러리를 추가하려면:
```cmake
target_link_libraries(robot_node ${catkin_LIBRARIES} ${OpenCV_LIBS})
```
이렇게 하면 OpenCV 기능도 사용할 수 있게 된다.

---

## **🔥 `CMakeLists.txt`에서 실행 파일을 설정하는 전체 과정**
ROS 패키지를 만들고 실행 파일을 빌드하는 전체 과정:
```cmake
cmake_minimum_required(VERSION 3.0.2)
project(my_robot)

# Catkin 패키지 설정
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)

# 실행 파일 생성
add_executable(robot_node src/main.cpp src/robot_controller.cpp)

# Catkin 라이브러리와 연결
target_link_libraries(robot_node ${catkin_LIBRARIES})

# 메시지 패키지 설정 (필요한 경우)
add_dependencies(robot_node ${catkin_EXPORTED_TARGETS})
```

---

## **🔥 실행 파일 빌드 및 실행 방법**
1️⃣ **빌드 실행 (`catkin_make`)**
```bash
cd ~/catkin_ws
catkin_make
```

2️⃣ **빌드 후 실행 가능 여부 확인**
```bash
roscd my_robot
ls devel/lib/my_robot/
```
👉 `robot_node` 실행 파일이 생성되어 있어야 함.

3️⃣ **노드 실행**
```bash
rosrun my_robot robot_node
```
🚀 이제 `robot_node` ROS 노드가 실행됨!

---

## **📌 결론**
| 명령어 | 역할 |
|--------|--------------------------|
| `add_executable(robot_node src/main.cpp)` | `robot_node` 실행 파일을 생성 |
| `target_link_libraries(robot_node ${catkin_LIBRARIES})` | ROS 라이브러리를 연결하여 ROS API를 사용할 수 있도록 함 |
| `catkin_make` | CMakeLists를 기반으로 빌드 실행 |

👉 **즉, `add_executable()`은 실행 파일을 만들고, `target_link_libraries()`는 해당 실행 파일이 ROS API를 사용할 수 있도록 설정하는 역할을 함.** 🚀


<br>
<br>
<br>
<br>

### 🚀 **ROS1 패키지 (`my_robot`) 전체 구조 및 코드 예제**  
CMake 파일이 위처럼 구성되어 있을 때의 **워크스페이스(WS) 디렉토리 구조**와 **필수 코드**를 간단하게 만들어 드릴게요.

---

## **📂 1. 워크스페이스 디렉토리 구조**
```bash
~/catkin_ws/
│── src/
│   ├── CMakeLists.txt  # catkin 기본 CMakeLists (수정하지 않음)
│   ├── my_robot/        # ROS 패키지
│   │   ├── CMakeLists.txt  # 패키지별 CMake 파일 (위 코드)
│   │   ├── package.xml     # 패키지 정보
│   │   ├── launch/
│   │   │   ├── my_robot.launch  # 노드 실행을 위한 launch 파일
│   │   ├── src/
│   │   │   ├── main.cpp         # ROS 노드 엔트리 포인트
│   │   │   ├── robot_controller.cpp  # 핵심 로직 파일
│   │   ├── include/
│   │   │   ├── my_robot/   
│   │   │   │   ├── robot_controller.hpp  # 헤더 파일
│   │   ├── config/
│   │   │   ├── params.yaml  # 파라미터 설정 파일 (옵션)
│   │   ├── msg/
│   │   │   ├── CustomMessage.msg  # (사용할 경우)
```

---

## **📜 2. `package.xml` (패키지 메타데이터)**
📌 **필수 의존성인 `roscpp`, `std_msgs` 추가**
```xml
<package format="2">
  <name>my_robot</name>
  <version>0.0.1</version>
  <description>A simple ROS package</description>

  <maintainer email="user@example.com">Your Name</maintainer>
  <license>BSD</license>

  <buildtool_depend>catkin</buildtool_depend>

  <depend>roscpp</depend>
  <depend>std_msgs</depend>

  <export></export>
</package>
```

---

## **📜 3. `src/main.cpp` (ROS 노드 엔트리 포인트)**
📌 **ROS 노드를 초기화하고 `robot_controller.cpp`의 클래스를 실행**
```cpp
#include "ros/ros.h"
#include "my_robot/robot_controller.hpp"

int main(int argc, char **argv) {
    ros::init(argc, argv, "robot_node");  // ROS 노드 초기화
    ros::NodeHandle nh;                   // ROS 노드 핸들 생성

    RobotController controller(nh);
    controller.run();

    return 0;
}
```

---

## **📜 4. `src/robot_controller.cpp` (핵심 로직)**
📌 **토픽을 구독(`Subscriber`)하고, 데이터를 처리하는 로직**
```cpp
#include "my_robot/robot_controller.hpp"
#include "std_msgs/String.h"

RobotController::RobotController(ros::NodeHandle& nh) : nh_(nh) {
    sub_ = nh_.subscribe("chatter", 10, &RobotController::callback, this);
    ROS_INFO("RobotController initialized!");
}

void RobotController::callback(const std_msgs::String::ConstPtr& msg) {
    ROS_INFO("Received: %s", msg->data.c_str());
}

void RobotController::run() {
    ros::spin();
}
```

---

## **📜 5. `include/my_robot/robot_controller.hpp` (클래스 선언)**
📌 **ROS 구독자를 관리하는 `RobotController` 클래스**
```cpp
#ifndef ROBOT_CONTROLLER_H
#define ROBOT_CONTROLLER_H

#include "ros/ros.h"
#include "std_msgs/String.h"

class RobotController {
public:
    RobotController(ros::NodeHandle& nh);
    void run();

private:
    ros::NodeHandle nh_;
    ros::Subscriber sub_;

    void callback(const std_msgs::String::ConstPtr& msg);
};

#endif
```

---

## **📜 6. `launch/my_robot.launch` (노드 실행)**
📌 **`robot_node`를 실행하는 launch 파일**
```xml
<launch>
    <node pkg="my_robot" type="robot_node" name="robot_node" output="screen"/>
</launch>
```

---

## **📜 7. `config/params.yaml` (파라미터 설정 - 옵션)**
📌 **ROS 파라미터를 설정할 경우 YAML 파일로 관리 가능**
```yaml
robot:
  speed: 1.0
  mode: "autonomous"
```

---

## **🚀 8. 빌드 및 실행 방법**
### ✅ 1️⃣ `catkin_make` 실행 (빌드)
```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash  # 빌드 후 환경 변수 설정
```

### ✅ 2️⃣ 노드 실행 방법
#### **🔹 1) 직접 실행 (`rosrun`)**
```bash
rosrun my_robot robot_node
```

#### **🔹 2) Launch 파일 실행 (`roslaunch`)**
```bash
roslaunch my_robot my_robot.launch
```

---

## **🔥 최종 정리**
✔ **ROS 패키지 기본 구조를 갖춘 실행 가능한 프로젝트**  
✔ **`roscpp` 기반의 ROS 노드(`robot_node`) 실행 가능**  
✔ **CMake 설정에 맞춰 `catkin_make`로 빌드 가능**  
✔ **`launch` 파일로 실행 자동화 가능**  

이제 이 구조를 기반으로 ROS 개발을 확장할 수 있습니다! 🚀🔥


<br>
<br>
<br>
<br>
네, 맞습니다! `"robot_node"`는 **ROS에서 실행되는 노드의 이름**이며, 이를 이해하기 위해 **`CMakeLists.txt`**, **`main.cpp`**, **`roslaunch` 명령어 실행 방식**을 하나씩 분석해 보겠습니다. 🚀

---

## 🔥 **1. `"robot_node"`란 무엇인가?**
- `"robot_node"`는 **CMake에서 만든 실행 파일의 이름**일 수도 있고,
- `"robot_node"`는 **ROS에서 실제 실행되는 노드의 이름**일 수도 있습니다.
- 이 둘은 다를 수도 있고, 같을 수도 있습니다.

---

## ✅ **2. `CMakeLists.txt`에서의 `"robot_node"` 의미**
```cmake
add_executable(robot_node src/main.cpp src/robot_controller.cpp)
target_link_libraries(robot_node ${catkin_LIBRARIES})
```
📌 **설명:**  
- `add_executable(robot_node ...)`  
  → `robot_node`라는 **실행 가능한 바이너리를 빌드**함.  
- `target_link_libraries(robot_node ${catkin_LIBRARIES})`  
  → `robot_node` 바이너리가 ROS 관련 라이브러리를 사용할 수 있도록 설정.

**💡 즉, `robot_node`는 ROS 패키지의 실행 가능한 프로그램(바이너리)의 이름이 됨.**  
**빌드 후 `~/catkin_ws/devel/lib/my_robot/robot_node` 실행 파일이 생성됨.**

---

## ✅ **3. `main.cpp`에서의 `"robot_node"` 의미**
```cpp
int main(int argc, char **argv) {
    ros::init(argc, argv, "robot_node");  // ROS 노드 이름 설정
    ros::NodeHandle nh;
    
    RobotController controller(nh);
    controller.run();

    return 0;
}
```
📌 **설명:**  
- `ros::init(argc, argv, "robot_node");`  
  → ROS 네트워크에서 실행될 때 이 노드의 **이름**을 `"robot_node"`로 설정.  
- **이 노드가 ROS Master에 등록될 때 이름이 `"robot_node"`가 됨.**

**💡 즉, `ros::init(..., "robot_node")` 때문에 ROS 네트워크에서 이 노드는 `"robot_node"`라는 이름을 가짐.**  

---

## ✅ **4. `rosrun`과 `roslaunch` 실행 시 `"robot_node"` 의미**
### **🔹 `rosrun` 실행 방식**
```bash
rosrun my_robot robot_node
```
📌 **설명:**  
- `"my_robot"`: **패키지 이름**
- `"robot_node"`: **실행 파일 이름** (`add_executable(robot_node ...)`에서 지정한 이름)

✔ **이 실행 파일(`~/catkin_ws/devel/lib/my_robot/robot_node`)이 실행됨.**  
✔ `main.cpp`에서 `ros::init(..., "robot_node")`을 호출했으므로, ROS 네트워크에서 노드 이름이 `"robot_node"`가 됨.

---

### **🔹 `roslaunch` 실행 방식**
```xml
<launch>
    <node pkg="my_robot" type="robot_node" name="custom_node_name" output="screen"/>
</launch>
```
```bash
roslaunch my_robot my_robot.launch
```
📌 **설명:**  
- `"pkg="my_robot"` → `my_robot` 패키지에서 실행할 노드를 찾음.
- `"type="robot_node"` → `CMakeLists.txt`에서 `add_executable(robot_node ...)`로 만든 실행 파일을 실행.
- `"name="custom_node_name"` → **ROS 네트워크에서 노드 이름을 `"custom_node_name"`으로 변경**.

✔ **이 경우, 실행되는 파일은 `robot_node` 바이너리이지만, ROS 네트워크에서 등록되는 이름은 `"custom_node_name"`이 됨.**  
✔ `rosnode list`로 확인하면 `"custom_node_name"`이 보이게 됨.

---

## 🔥 **5. 최종 정리**
| 코드 또는 명령어 | `"robot_node"`의 역할 |
|-----------------|------------------|
| `add_executable(robot_node ...)` (CMake) | **실행 파일 이름 (바이너리)** |
| `ros::init(..., "robot_node")` (C++) | **ROS 네트워크에서 노드 이름** |
| `rosrun my_robot robot_node` | **바이너리 실행 (CMake에서 만든 실행 파일 실행)** |
| `roslaunch`의 `<node name="custom_node_name"/>` | **ROS 네트워크에서 실행될 노드의 이름을 `"custom_node_name"`으로 변경** |

**🚀 즉, `robot_node`는 원래 실행 파일 이름이지만, `ros::init()`을 통해 ROS 노드의 이름도 `"robot_node"`로 설정됨.**  
**하지만, `roslaunch`에서 `name="..."`을 지정하면 실행 파일 이름과 다르게 노드가 등록될 수도 있음.** 🚀


<br>
<br>
<br>
<br>
네! 기존 C++ 기반 ROS1 코드 구조를 **Python 기반 ROS1 코드**로 동일하게 작성해 드릴게요.  
Python에서는 `rospy`를 사용하며, 실행 파일(`robot_node`) 대신 **Python 스크립트(`robot_node.py`)를 실행**하게 됩니다.

---

## **📂 1. 워크스페이스 디렉토리 구조 (Python 버전)**
```bash
~/catkin_ws/
│── src/
│   ├── CMakeLists.txt  # catkin 기본 CMakeLists (수정하지 않음)
│   ├── my_robot/        # ROS 패키지
│   │   ├── CMakeLists.txt  # 패키지별 CMake 파일
│   │   ├── package.xml     # 패키지 정보
│   │   ├── launch/
│   │   │   ├── my_robot.launch  # 노드 실행을 위한 launch 파일
│   │   ├── scripts/
│   │   │   ├── robot_node.py         # ROS 노드 엔트리 포인트
│   │   │   ├── robot_controller.py  # 핵심 로직 파일
│   │   ├── config/
│   │   │   ├── params.yaml  # 파라미터 설정 파일 (옵션)
│   │   ├── msg/
│   │   │   ├── CustomMessage.msg  # (사용할 경우)
```
🚀 **Python 버전에서는 실행 파일 대신 `scripts/` 디렉토리 안에 Python 스크립트를 사용합니다.**  
🚀 **실행 권한이 필요하므로 `chmod +x robot_node.py`를 해야 실행됩니다.**

---

## **📜 2. `package.xml` (Python 버전)**
📌 **Python에서도 `rospy`, `std_msgs` 의존성을 추가해야 합니다.**
```xml
<package format="2">
  <name>my_robot</name>
  <version>0.0.1</version>
  <description>A simple ROS package (Python version)</description>

  <maintainer email="user@example.com">Your Name</maintainer>
  <license>BSD</license>

  <buildtool_depend>catkin</buildtool_depend>

  <depend>rospy</depend>
  <depend>std_msgs</depend>

  <export></export>
</package>
```

---

## **📜 3. `scripts/robot_node.py` (ROS 노드 엔트리 포인트)**
📌 **ROS 노드를 초기화하고 `robot_controller.py`의 클래스를 실행**
```python
#!/usr/bin/env python3
import rospy
from robot_controller import RobotController

def main():
    rospy.init_node("robot_node")  # ROS 노드 초기화
    controller = RobotController()
    controller.run()

if __name__ == "__main__":
    main()
```
✅ **Python 스크립트는 실행 권한을 부여해야 실행됨.**
```bash
chmod +x ~/catkin_ws/src/my_robot/scripts/robot_node.py
```

---

## **📜 4. `scripts/robot_controller.py` (핵심 로직)**
📌 **토픽을 구독(`Subscriber`)하고 데이터를 처리하는 로직**
```python
import rospy
from std_msgs.msg import String

class RobotController:
    def __init__(self):
        self.sub = rospy.Subscriber("chatter", String, self.callback)
        rospy.loginfo("RobotController initialized!")

    def callback(self, msg):
        rospy.loginfo(f"Received: {msg.data}")

    def run(self):
        rospy.spin()
```
🚀 **C++ 코드와 동일한 기능을 하는 Python 코드입니다!**

---

## **📜 5. `launch/my_robot.launch` (노드 실행)**
📌 **Python 노드 실행을 위한 launch 파일**
```xml
<launch>
    <node pkg="my_robot" type="robot_node.py" name="robot_node" output="screen"/>
</launch>
```
🚀 **Python 실행 파일은 확장자 `.py`를 반드시 포함해야 합니다.**

---

## **📜 6. `config/params.yaml` (파라미터 설정 - 옵션)**
📌 **ROS 파라미터를 설정할 경우 YAML 파일로 관리 가능**
```yaml
robot:
  speed: 1.0
  mode: "autonomous"
```

---

## **🚀 7. 실행 방법**
### ✅ 1️⃣ `catkin_make` 실행 (빌드) → **Python 버전에서는 불필요**
Python 코드만 실행하는 경우 **`catkin_make` 없이도 실행 가능**하지만, 패키지를 인식하려면 `source` 명령어가 필요합니다.
```bash
cd ~/catkin_ws
source devel/setup.bash
```

### ✅ 2️⃣ 노드 실행 방법
#### **🔹 1) 직접 실행 (`rosrun`)**
```bash
rosrun my_robot robot_node.py
```
🚀 실행 후 `rostopic pub /chatter std_msgs/String "Hello ROS!"` 명령어를 실행하면 로그가 출력됨.

#### **🔹 2) Launch 파일 실행 (`roslaunch`)**
```bash
roslaunch my_robot my_robot.launch
```

---

## **🔥 최종 정리**
✔ **Python 기반 ROS 패키지 기본 구조**  
✔ **`rospy`를 사용하여 ROS 노드(`robot_node.py`) 실행 가능**  
✔ **C++ 코드와 기능적으로 동일하게 작동**  
✔ **Python은 `catkin_make` 없이 실행 가능하지만, 실행 전에 `chmod +x` 필요**  

이제 Python 기반 ROS 패키지를 쉽게 개발할 수 있습니다! 🚀🔥

<br>
<br>
<br>
<br>
맞아요! **C++과 Python에서 ROS 노드 이름을 다루는 방식이 조금 다르기 때문에 헷갈릴 수 있습니다.**  
다시 한 번 정리해 보면:

---

## **🚀 C++ vs. Python의 ROS 노드 네이밍 차이**
| 언어 | 실행 파일 이름 | ROS 네트워크에서 노드 이름 |
|------|-------------|------------------|
| **C++** | `add_executable(robot_node ...)`에서 지정한 실행 파일 이름 | `ros::init(..., "robot_node")`에서 설정한 노드 이름 |
| **Python** | 스크립트 파일 이름 (`robot_node.py`) | **파일 이름과 동일 (기본값)**, 하지만 `rospy.init_node()`에서 변경 가능 |

---

### **📌 C++에서의 동작 방식**
```cmake
add_executable(robot_node src/main.cpp src/robot_controller.cpp)
```
- **실행 파일(`robot_node`)이 생성됨.**
- 하지만, `main.cpp`에서 **ROS 네트워크에 등록할 노드 이름을 다르게 설정 가능.**
```cpp
ros::init(argc, argv, "custom_robot_node");  // 노드 이름을 "custom_robot_node"로 설정
```
- 이렇게 하면 실행 파일 이름은 `robot_node`지만, ROS 네트워크에서는 **"custom_robot_node"라는 이름으로 등록**됨.

#### **🚀 실행 결과**
```bash
rosrun my_robot robot_node
```
```bash
rosnode list
```
```
/custom_robot_node  # 실행 파일 이름(robot_node)과 다름!
```

---

### **📌 Python에서의 동작 방식**
```xml
<node pkg="my_robot" type="robot_node.py" name="robot_node" output="screen"/>
```
- Python에서는 실행 파일(`robot_node.py`)이 **기본적으로 노드 이름이 됨.**
- 하지만, `rospy.init_node()`에서 노드 이름을 변경 가능.

```python
rospy.init_node("custom_robot_node")  # 실행 파일 이름과 다르게 설정 가능
```

#### **🚀 실행 결과**
```bash
rosrun my_robot robot_node.py
```
```bash
rosnode list
```
```
/custom_robot_node  # Python에서도 기본 파일명과 다르게 설정 가능!
```

---

## **🔥 결론**
- **C++에서는 실행 파일 이름(`add_executable`)과 ROS 네트워크에서 등록된 노드 이름이 다를 수 있음.**
- **Python에서는 실행 파일(`.py`)의 이름이 기본적으로 ROS 네트워크에서 등록되는 노드 이름이지만, 변경 가능.**
- **Launch 파일에서 `<node name="..."/>`을 설정하면 C++/Python 상관없이 ROS 네트워크에서 노드 이름을 바꿀 수 있음.** 🚀

이제 완벽하게 이해됐을 거예요! 🎯🔥

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
<br>
