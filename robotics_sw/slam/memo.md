아래는 ROS2 C++ 프로젝트의 main.cpp 코드입니다.
이 코드는 하나의 노드에서 여러 개의 토픽과 서비스를 실행하도록 설계되었습니다.


---

📌 1️⃣ main.cpp

#include "rclcpp/rclcpp.hpp"
#include "robot_node.hpp"

int main(int argc, char *argv[])
{
    // ROS2 초기화
    rclcpp::init(argc, argv);

    // RobotNode 생성
    auto node = std::make_shared<RobotNode>();

    // 노드를 실행 (싱글 스레드 실행)
    rclcpp::spin(node);

    // 종료 후 정리
    rclcpp::shutdown();
    return 0;
}


---

📌 2️⃣ main.cpp 설명

1) ROS2 초기화

rclcpp::init(argc, argv);

ROS2 노드를 실행하기 위해 초기화합니다.



---

2) 로봇 노드 실행

auto node = std::make_shared<RobotNode>();

robot_node.hpp와 robot_node.cpp에서 정의한 RobotNode 객체를 생성합니다.



---

3) 노드 실행 (spin)

rclcpp::spin(node);

ROS2 노드를 계속 실행하면서 메시지를 처리합니다.

spin()을 사용하면 노드가 지속적으로 동작하며 퍼블리셔, 서브스크라이버, 서비스 요청을 처리합니다.



---

4) ROS2 종료

rclcpp::shutdown();

프로그램 종료 시 ROS2를 정리합니다.



---

📌 3️⃣ main.cpp 실행 흐름

1. ROS2 초기화


2. RobotNode 생성


3. 퍼블리셔가 주기적으로 robot_status와 battery_level을 퍼블리시


4. 서브스크라이버가 command_topic을 수신


5. 여러 개의 서비스 요청을 처리 (add_two_ints_extended, factorial, fibonacci, is_prime, gcd)


6. 사용자가 종료 (Ctrl + C)하면, ROS2 종료 후 프로그램 정리




---

📌 4️⃣ 빌드 및 실행

1️⃣ CMakeLists.txt 업데이트 (새로운 서비스 추가)

cmake_minimum_required(VERSION 3.8)
project(my_ros2_system)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(example_interfaces REQUIRED)

include_directories(include)

add_executable(robot_main src/main.cpp src/robot_node.cpp src/math_utils.cpp)
ament_target_dependencies(robot_main rclcpp example_interfaces)

install(TARGETS robot_main
  DESTINATION lib/${PROJECT_NAME})

ament_package()


---

2️⃣ 빌드

colcon build --packages-select my_ros2_system


---

3️⃣ 실행

ros2 run my_ros2_system robot_main


---

🚀 결론

main.cpp에서는 RobotNode를 실행하고 관리만 수행.

robot_node.cpp가 모든 퍼블리셔, 서브스크라이버, 서비스 기능을 처리.

math_utils.cpp에서 복잡한 연산을 담당.

C++과 Python 모두 동일한 구조로 실행 가능.


이제 robot_main을 실행하고, 여러 개의 토픽과 서비스를 테스트해보세요! 🚀😃







아래는 **ROS2 C++ 프로젝트의 `main.cpp` 코드**입니다.  
이 코드는 **하나의 노드에서 여러 개의 토픽과 서비스를 실행**하도록 설계되었습니다.

---

# **📌 1️⃣ `main.cpp`**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "robot_node.hpp"

int main(int argc, char *argv[])
{
    // ROS2 초기화
    rclcpp::init(argc, argv);

    // RobotNode 생성
    auto node = std::make_shared<RobotNode>();

    // 노드를 실행 (싱글 스레드 실행)
    rclcpp::spin(node);

    // 종료 후 정리
    rclcpp::shutdown();
    return 0;
}
```

---

# **📌 2️⃣ `main.cpp` 설명**
### **1) ROS2 초기화**
```cpp
rclcpp::init(argc, argv);
```
- ROS2 노드를 실행하기 위해 **초기화**합니다.

---

### **2) 로봇 노드 실행**
```cpp
auto node = std::make_shared<RobotNode>();
```
- `robot_node.hpp`와 `robot_node.cpp`에서 정의한 **RobotNode 객체를 생성**합니다.

---

### **3) 노드 실행 (`spin`)**
```cpp
rclcpp::spin(node);
```
- **ROS2 노드를 계속 실행하면서 메시지를 처리**합니다.
- `spin()`을 사용하면 노드가 지속적으로 동작하며 **퍼블리셔, 서브스크라이버, 서비스 요청을 처리**합니다.

---

### **4) ROS2 종료**
```cpp
rclcpp::shutdown();
```
- 프로그램 종료 시 **ROS2를 정리**합니다.

---

# **📌 3️⃣ `main.cpp` 실행 흐름**
1. **ROS2 초기화**
2. **RobotNode 생성**
3. **퍼블리셔가 주기적으로 `robot_status`와 `battery_level`을 퍼블리시**
4. **서브스크라이버가 `command_topic`을 수신**
5. **여러 개의 서비스 요청을 처리 (`add_two_ints_extended`, `factorial`, `fibonacci`, `is_prime`, `gcd`)**
6. **사용자가 종료 (`Ctrl + C`)하면, ROS2 종료 후 프로그램 정리**

---

# **📌 4️⃣ 빌드 및 실행**
## **1️⃣ CMakeLists.txt 업데이트 (새로운 서비스 추가)**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_ros2_system)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(example_interfaces REQUIRED)

include_directories(include)

add_executable(robot_main src/main.cpp src/robot_node.cpp src/math_utils.cpp)
ament_target_dependencies(robot_main rclcpp example_interfaces)

install(TARGETS robot_main
  DESTINATION lib/${PROJECT_NAME})

ament_package()
```

---

## **2️⃣ 빌드**
```sh
colcon build --packages-select my_ros2_system
```

---

## **3️⃣ 실행**
```sh
ros2 run my_ros2_system robot_main
```

---

# **🚀 결론**
- **`main.cpp`에서는 `RobotNode`를 실행하고 관리만 수행**.
- **`robot_node.cpp`가 모든 퍼블리셔, 서브스크라이버, 서비스 기능을 처리**.
- **`math_utils.cpp`에서 복잡한 연산을 담당**.
- **C++과 Python 모두 동일한 구조로 실행 가능**.

이제 `robot_main`을 실행하고, 여러 개의 토픽과 서비스를 테스트해보세요! 🚀😃







아래는 **ROS2 C++ 프로젝트의 `main.cpp` 코드**입니다.  
이 코드는 **하나의 노드에서 여러 개의 토픽과 서비스를 실행**하도록 설계되었습니다.

---

# **📌 1️⃣ `main.cpp`**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "robot_node.hpp"

int main(int argc, char *argv[])
{
    // ROS2 초기화
    rclcpp::init(argc, argv);

    // RobotNode 생성
    auto node = std::make_shared<RobotNode>();

    // 노드를 실행 (싱글 스레드 실행)
    rclcpp::spin(node);

    // 종료 후 정리
    rclcpp::shutdown();
    return 0;
}
```

---

# **📌 2️⃣ `main.cpp` 설명**
### **1) ROS2 초기화**
```cpp
rclcpp::init(argc, argv);
```
- ROS2 노드를 실행하기 위해 **초기화**합니다.

---

### **2) 로봇 노드 실행**
```cpp
auto node = std::make_shared<RobotNode>();
```
- `robot_node.hpp`와 `robot_node.cpp`에서 정의한 **RobotNode 객체를 생성**합니다.

---

### **3) 노드 실행 (`spin`)**
```cpp
rclcpp::spin(node);
```
- **ROS2 노드를 계속 실행하면서 메시지를 처리**합니다.
- `spin()`을 사용하면 노드가 지속적으로 동작하며 **퍼블리셔, 서브스크라이버, 서비스 요청을 처리**합니다.

---

### **4) ROS2 종료**
```cpp
rclcpp::shutdown();
```
- 프로그램 종료 시 **ROS2를 정리**합니다.

---

# **📌 3️⃣ `main.cpp` 실행 흐름**
1. **ROS2 초기화**
2. **RobotNode 생성**
3. **퍼블리셔가 주기적으로 `robot_status`와 `battery_level`을 퍼블리시**
4. **서브스크라이버가 `command_topic`을 수신**
5. **여러 개의 서비스 요청을 처리 (`add_two_ints_extended`, `factorial`, `fibonacci`, `is_prime`, `gcd`)**
6. **사용자가 종료 (`Ctrl + C`)하면, ROS2 종료 후 프로그램 정리**

---

# **📌 4️⃣ 빌드 및 실행**
## **1️⃣ CMakeLists.txt 업데이트 (새로운 서비스 추가)**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_ros2_system)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(example_interfaces REQUIRED)

include_directories(include)

add_executable(robot_main src/main.cpp src/robot_node.cpp src/math_utils.cpp)
ament_target_dependencies(robot_main rclcpp example_interfaces)

install(TARGETS robot_main
  DESTINATION lib/${PROJECT_NAME})

ament_package()
```

---

## **2️⃣ 빌드**
```sh
colcon build --packages-select my_ros2_system
```

---

## **3️⃣ 실행**
```sh
ros2 run my_ros2_system robot_main
```

---

# **🚀 결론**
- **`main.cpp`에서는 `RobotNode`를 실행하고 관리만 수행**.
- **`robot_node.cpp`가 모든 퍼블리셔, 서브스크라이버, 서비스 기능을 처리**.
- **`math_utils.cpp`에서 복잡한 연산을 담당**.
- **C++과 Python 모두 동일한 구조로 실행 가능**.

이제 `robot_main`을 실행하고, 여러 개의 토픽과 서비스를 테스트해보세요! 🚀😃
