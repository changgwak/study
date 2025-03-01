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
