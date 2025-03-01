네! **ROS1에서 패키지를 만들 때 `catkin_create_pkg` 명령어를 사용**하는데, 이때 여러 **파라미터나 설정을 추가**할 수 있습니다.  
각 옵션을 예제로 설명해드릴게요! 🚀  

---

## **🚀 1. 기본적인 패키지 생성**
### ✅ **명령어 기본형**
```bash
catkin_create_pkg <패키지명> <의존성1> <의존성2> ...
```
📌 **예제 1: `my_robot` 패키지 생성**
```bash
catkin_create_pkg my_robot roscpp std_msgs
```
✔ `my_robot`라는 패키지를 생성  
✔ `roscpp`, `std_msgs` 패키지를 **의존성으로 추가**  

📌 **생성된 디렉토리 구조**
```
my_robot/
│── CMakeLists.txt
│── package.xml
│── src/
│── include/my_robot/
```
✅ `package.xml`과 `CMakeLists.txt`가 자동으로 생성됨  
✅ `src/`와 `include/` 디렉토리는 기본적으로 비어 있음  

---

## **🚀 2. 여러 개의 의존성 추가**
📌 **예제 2: `geometry_msgs`, `sensor_msgs`, `tf` 추가**
```bash
catkin_create_pkg my_robot roscpp std_msgs geometry_msgs sensor_msgs tf
```
✔ `geometry_msgs`, `sensor_msgs`, `tf` 라이브러리까지 의존성 포함  

📌 **추가된 의존성 확인 (`package.xml`)**
```xml
<depend>geometry_msgs</depend>
<depend>sensor_msgs</depend>
<depend>tf</depend>
```

📌 **추가된 `CMakeLists.txt`**
```cmake
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  geometry_msgs
  sensor_msgs
  tf
)
```
✅ 이제 `geometry_msgs`, `sensor_msgs`, `tf` 메시지를 사용할 수 있음!

---

## **🚀 3. Python 기반 패키지 생성 (`rospy`)**
📌 **예제 3: Python 패키지**
```bash
catkin_create_pkg my_python_robot rospy std_msgs
```
✔ `rospy`(Python) 기반으로 `std_msgs` 메시지를 사용할 수 있는 패키지 생성  
✔ 실행 파일(`.py`)은 `scripts/` 폴더에 저장해야 함  

📌 **Python 패키지는 `CMakeLists.txt` 수정 없이 사용 가능**  
```bash
rosrun my_python_robot my_script.py
```

---

## **🚀 4. OpenCV, PCL, MoveIt! 등 외부 라이브러리 추가**
📌 **예제 4: OpenCV, PCL (Point Cloud Library) 추가**
```bash
catkin_create_pkg my_vision_robot roscpp std_msgs sensor_msgs cv_bridge pcl_ros
```
✔ OpenCV(`cv_bridge`)와 PCL(`pcl_ros`)을 사용할 수 있는 패키지 생성  

📌 **추가된 `package.xml`**
```xml
<depend>cv_bridge</depend>
<depend>pcl_ros</depend>
```

📌 **추가된 `CMakeLists.txt`**
```cmake
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  sensor_msgs
  cv_bridge
  pcl_ros
)
```

---

## **🚀 5. 실행 파일 생성 옵션**
📌 **예제 5: 패키지 생성 후 실행 파일 추가**
```bash
catkin_create_pkg my_robot roscpp std_msgs
```
✔ 기본 패키지 생성 후 `src/` 안에 실행 파일(`.cpp`)을 추가해야 함.

📌 **`src/main.cpp` 생성**
```cpp
#include "ros/ros.h"

int main(int argc, char **argv) {
    ros::init(argc, argv, "my_robot_node");
    ros::NodeHandle nh;

    ROS_INFO("My Robot Node Started!");
    ros::spin();

    return 0;
}
```
📌 **`CMakeLists.txt` 수정 (실행 파일 등록)**
```cmake
add_executable(my_robot_node src/main.cpp)
target_link_libraries(my_robot_node ${catkin_LIBRARIES})
```

📌 **빌드 후 실행**
```bash
catkin_make
rosrun my_robot my_robot_node
```

---

## **🚀 6. 템플릿 없이 빈 패키지만 생성**
📌 **예제 6: `--no-deps` 옵션 (의존성 없이 빈 패키지)**
```bash
catkin_create_pkg empty_package --no-deps
```
✔ `package.xml`, `CMakeLists.txt` 파일만 생성됨  
✔ ROS 패키지 내부에서 특정 기능을 하지 않고, 단순한 폴더 역할을 할 때 사용  

---

## **🔥 최종 정리**
| 명령어 | 설명 |
|--------|------|
| `catkin_create_pkg my_robot roscpp std_msgs` | 기본 패키지 생성 |
| `catkin_create_pkg my_robot roscpp std_msgs geometry_msgs tf` | 여러 개의 의존성 추가 |
| `catkin_create_pkg my_python_robot rospy std_msgs` | Python 패키지 생성 |
| `catkin_create_pkg my_vision_robot roscpp std_msgs cv_bridge pcl_ros` | OpenCV 및 PCL 사용 가능 |
| `catkin_create_pkg empty_package --no-deps` | 빈 패키지 생성 |

이제 `catkin_create_pkg`를 자유롭게 활용해서 다양한 ROS 패키지를 만들 수 있습니다! 🚀🔥


<br>
<br>
<br>
<br>

### 🚀 **CMakeLists.txt 및 package.xml 수정 방법 (파일이 여러 개일 때)**
패키지를 만들 때 **src, include 디렉토리에 여러 개의 소스 파일과 헤더 파일을 추가**하는 경우,  
`CMakeLists.txt` 및 `package.xml`에서 몇 가지 설정을 추가해야 합니다.  
각 단계별로 설명해드릴게요. 🎯

---

## **📂 1. 프로젝트 디렉토리 구조 예시**
📌 **C++ 프로젝트에서 여러 개의 소스파일과 헤더파일을 포함한 경우**
```bash
~/catkin_ws/
│── src/
│   ├── my_robot/               # ROS 패키지
│   │   ├── CMakeLists.txt      # CMake 설정
│   │   ├── package.xml         # 패키지 메타데이터
│   │   ├── launch/
│   │   │   ├── my_robot.launch # 실행 설정
│   │   ├── src/
│   │   │   ├── main.cpp        # 엔트리 포인트
│   │   │   ├── robot_controller.cpp  # 로봇 컨트롤러
│   │   │   ├── sensor_manager.cpp    # 센서 데이터 처리
│   │   ├── include/
│   │   │   ├── my_robot/
│   │   │   │   ├── robot_controller.hpp  # 로봇 컨트롤러 헤더
│   │   │   │   ├── sensor_manager.hpp    # 센서 데이터 처리 헤더
```

---

## **📜 2. `package.xml` 수정**
📌 **사용할 라이브러리 및 의존성 추가 (`roscpp`, `std_msgs`, `sensor_msgs`)**
```xml
<package format="2">
  <name>my_robot</name>
  <version>0.0.1</version>
  <description>A multi-file ROS package</description>

  <maintainer email="user@example.com">Your Name</maintainer>
  <license>BSD</license>

  <buildtool_depend>catkin</buildtool_depend>

  <!-- C++ 노드에서 사용할 ROS 패키지 의존성 -->
  <depend>roscpp</depend>
  <depend>std_msgs</depend>
  <depend>sensor_msgs</depend>

  <export></export>
</package>
```
✅ **`roscpp`, `std_msgs`, `sensor_msgs`를 의존성으로 추가**  
✅ **새로운 기능이 추가되면 `depend` 태그를 업데이트해야 함**  

---

## **📜 3. `CMakeLists.txt` 수정**
📌 **여러 개의 소스 파일과 헤더 파일을 포함하는 경우**
```cmake
cmake_minimum_required(VERSION 3.0.2)
project(my_robot)

# Catkin 패키지 설정
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  sensor_msgs
)

# Include 디렉토리 추가
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

# 실행 파일 추가 (여러 개의 소스 파일 포함)
add_executable(robot_node src/main.cpp src/robot_controller.cpp src/sensor_manager.cpp)

# 실행 파일을 catkin 라이브러리와 연결
target_link_libraries(robot_node ${catkin_LIBRARIES})

# 메시지 패키지 설정 (필요한 경우)
add_dependencies(robot_node ${catkin_EXPORTED_TARGETS})
```
✅ **여러 개의 `.cpp` 파일(`main.cpp`, `robot_controller.cpp`, `sensor_manager.cpp`)을 `add_executable()`에 포함**  
✅ **`include_directories()`로 `include/` 디렉토리 추가**  
✅ **`target_link_libraries()`에서 `catkin_LIBRARIES`와 연결**  

---

## **📜 4. `src/main.cpp` (노드 엔트리 포인트)**
```cpp
#include "ros/ros.h"
#include "my_robot/robot_controller.hpp"
#include "my_robot/sensor_manager.hpp"

int main(int argc, char **argv) {
    ros::init(argc, argv, "robot_node");
    ros::NodeHandle nh;

    RobotController controller(nh);
    SensorManager sensor(nh);

    controller.run();
    sensor.start();

    return 0;
}
```
✅ **`robot_controller.hpp`, `sensor_manager.hpp` 포함하여 여러 기능을 함께 실행**

---

## **📜 5. `include/my_robot/robot_controller.hpp` (헤더 파일)**
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
✅ **로봇 컨트롤러 클래스 선언**

---

## **📜 6. `src/robot_controller.cpp` (소스 파일)**
```cpp
#include "my_robot/robot_controller.hpp"

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
✅ **ROS 토픽을 구독하는 컨트롤러 클래스 구현**

---

## **📜 7. `include/my_robot/sensor_manager.hpp` (헤더 파일)**
```cpp
#ifndef SENSOR_MANAGER_H
#define SENSOR_MANAGER_H

#include "ros/ros.h"
#include "sensor_msgs/LaserScan.h"

class SensorManager {
public:
    SensorManager(ros::NodeHandle& nh);
    void start();

private:
    ros::NodeHandle nh_;
    ros::Subscriber laser_sub_;

    void laserCallback(const sensor_msgs::LaserScan::ConstPtr& msg);
};

#endif
```
✅ **레이저 스캐너 센서 데이터를 구독하는 클래스 선언**

---

## **📜 8. `src/sensor_manager.cpp` (소스 파일)**
```cpp
#include "my_robot/sensor_manager.hpp"

SensorManager::SensorManager(ros::NodeHandle& nh) : nh_(nh) {
    laser_sub_ = nh_.subscribe("scan", 10, &SensorManager::laserCallback, this);
    ROS_INFO("SensorManager initialized!");
}

void SensorManager::laserCallback(const sensor_msgs::LaserScan::ConstPtr& msg) {
    ROS_INFO("Laser scan received, range: %f", msg->ranges[0]);
}

void SensorManager::start() {
    ros::spin();
}
```
✅ **센서 데이터를 구독하는 기능 구현**

---

## **📜 9. `launch/my_robot.launch` (노드 실행)**
```xml
<launch>
    <node pkg="my_robot" type="robot_node" name="robot_node" output="screen"/>
</launch>
```
✅ **여러 개의 기능을 포함한 `robot_node` 실행**

---

## **🚀 10. 빌드 및 실행**
### ✅ 1️⃣ `catkin_make` 실행 (빌드)
```bash
cd ~/catkin_ws
catkin_make
source devel/setup.bash
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
✔ **여러 개의 `.cpp` 및 `.hpp` 파일을 포함하는 프로젝트 구성 방법**  
✔ **`CMakeLists.txt`에서 `add_executable()`과 `include_directories()`를 활용하는 방법**  
✔ **`package.xml`에서 의존성을 추가하는 방법**  
✔ **여러 파일을 포함한 빌드 및 실행 방법**  

이제 ROS 패키지를 더욱 확장해서 사용할 수 있습니다! 🚀🔥

<br>
<br>
<br>
<br>
