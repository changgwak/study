이제 원래 구조대로 **ROS1 C++ 프로젝트를 완벽하게 구성**하겠습니다.  
즉, **하나의 `robot_node`에서 퍼블리셔, 서브스크라이버, 서비스 서버 및 클라이언트가 모두 포함**되도록 작성합니다.

---

# **📌 1️⃣ 프로젝트 개요**
| 기능 | 설명 |
|------|------|
| **토픽 (Topics)** | `robot_status` (퍼블리셔), `battery_level` (퍼블리셔), `command_topic` (구독) |
| **서비스 서버 (Service Server)** | `add_two_ints_extended`, `calculate_square`, `get_robot_status` |
| **서비스 클라이언트 (Service Client)** | `calculate_square` 서비스 요청 |

---

# **📌 2️⃣ ROS1 패키지 생성**
```sh
cd ~/catkin_ws/src
catkin_create_pkg my_ros1_system roscpp std_msgs message_generation message_runtime
```

---

# **📌 3️⃣ 서비스 메시지 정의**
```sh
cd ~/catkin_ws/src/my_ros1_system
mkdir srv
cd srv
```
#### **srv/AddTwoIntsExtended.srv**
```srv
int64 a
int64 b
---
int64 sum
string parity
```
#### **srv/CalculateSquare.srv**
```srv
int64 number
---
int64 square
```
#### **srv/GetRobotStatus.srv**
```srv
---
string status
float32 battery_level
```

---

# **📌 4️⃣ CMakeLists.txt 수정**
```cmake
find_package(catkin REQUIRED COMPONENTS roscpp std_msgs message_generation)

add_service_files(
  FILES
  AddTwoIntsExtended.srv
  CalculateSquare.srv
  GetRobotStatus.srv
)

generate_messages(DEPENDENCIES std_msgs)

catkin_package(CATKIN_DEPENDS roscpp std_msgs message_runtime)

include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(robot_node src/main.cpp src/robot_node.cpp src/math_utils.cpp)

target_link_libraries(robot_node ${catkin_LIBRARIES})

add_dependencies(robot_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
```

---

# **📌 5️⃣ package.xml 수정**
```xml
<build_depend>message_generation</build_depend>
<exec_depend>message_runtime</exec_depend>
```

---

# **📌 6️⃣ 유틸리티 함수 (`math_utils.hpp` & `math_utils.cpp`)**
## **🔹 `math_utils.hpp`**
```cpp
#ifndef MATH_UTILS_HPP
#define MATH_UTILS_HPP

#include <string>

class MathUtils
{
public:
    static int add(int a, int b);
    static std::string check_parity(int sum);
    static int calculate_square(int number);
};

#endif // MATH_UTILS_HPP
```

---
## **🔹 `math_utils.cpp`**
```cpp
#include "math_utils.hpp"

int MathUtils::add(int a, int b)
{
    return a + b;
}

std::string MathUtils::check_parity(int sum)
{
    return (sum % 2 == 0) ? "even" : "odd";
}

int MathUtils::calculate_square(int number)
{
    return number * number;
}
```

---

# **📌 7️⃣ 로봇 노드 (`robot_node.hpp` & `robot_node.cpp`)**
## **🔹 `robot_node.hpp`**
```cpp
#ifndef ROBOT_NODE_HPP
#define ROBOT_NODE_HPP

#include "ros/ros.h"
#include "std_msgs/String.h"
#include "std_msgs/Float32.h"
#include "my_ros1_system/AddTwoIntsExtended.h"
#include "my_ros1_system/CalculateSquare.h"
#include "my_ros1_system/GetRobotStatus.h"
#include "math_utils.hpp"

class RobotNode
{
public:
    RobotNode();

private:
    ros::NodeHandle nh_;

    // 퍼블리셔
    ros::Publisher status_publisher_;
    ros::Publisher battery_publisher_;

    // 서브스크라이버
    ros::Subscriber command_subscriber_;

    // 서비스 서버
    ros::ServiceServer add_two_ints_service_;
    ros::ServiceServer calculate_square_service_;
    ros::ServiceServer get_robot_status_service_;

    // 서비스 클라이언트
    ros::ServiceClient calculate_square_client_;

    void publish_status();
    void publish_battery();
    void command_callback(const std_msgs::String::ConstPtr &msg);

    // 서비스 서버 핸들러
    bool handle_add_two_ints(my_ros1_system::AddTwoIntsExtended::Request &req,
                             my_ros1_system::AddTwoIntsExtended::Response &res);
    bool handle_calculate_square(my_ros1_system::CalculateSquare::Request &req,
                                 my_ros1_system::CalculateSquare::Response &res);
    bool handle_get_robot_status(my_ros1_system::GetRobotStatus::Request &req,
                                 my_ros1_system::GetRobotStatus::Response &res);

    // 서비스 클라이언트 메서드
    void request_calculate_square(int number);
};

#endif // ROBOT_NODE_HPP
```

---

## **🔹 `robot_node.cpp`**
```cpp
#include "robot_node.hpp"

RobotNode::RobotNode()
{
    // 퍼블리셔 생성
    status_publisher_ = nh_.advertise<std_msgs::String>("robot_status", 10);
    battery_publisher_ = nh_.advertise<std_msgs::Float32>("battery_level", 10);

    // 서브스크라이버 생성
    command_subscriber_ = nh_.subscribe("command_topic", 10, &RobotNode::command_callback, this);

    // 서비스 서버 생성
    add_two_ints_service_ = nh_.advertiseService("add_two_ints_extended", &RobotNode::handle_add_two_ints, this);
    calculate_square_service_ = nh_.advertiseService("calculate_square", &RobotNode::handle_calculate_square, this);
    get_robot_status_service_ = nh_.advertiseService("get_robot_status", &RobotNode::handle_get_robot_status, this);

    // 서비스 클라이언트 생성
    calculate_square_client_ = nh_.serviceClient<my_ros1_system::CalculateSquare>("calculate_square");

    ROS_INFO("Robot Node Initialized.");
}

void RobotNode::publish_status()
{
    std_msgs::String msg;
    msg.data = "Robot is active.";
    status_publisher_.publish(msg);
}

void RobotNode::publish_battery()
{
    std_msgs::Float32 msg;
    msg.data = 75.5;
    battery_publisher_.publish(msg);
}

void RobotNode::command_callback(const std_msgs::String::ConstPtr &msg)
{
    ROS_INFO("Received Command: %s", msg->data.c_str());
}

bool RobotNode::handle_add_two_ints(my_ros1_system::AddTwoIntsExtended::Request &req,
                                    my_ros1_system::AddTwoIntsExtended::Response &res)
{
    res.sum = MathUtils::add(req.a, req.b);
    res.parity = MathUtils::check_parity(res.sum);
    return true;
}

bool RobotNode::handle_calculate_square(my_ros1_system::CalculateSquare::Request &req,
                                        my_ros1_system::CalculateSquare::Response &res)
{
    res.square = MathUtils::calculate_square(req.number);
    return true;
}

bool RobotNode::handle_get_robot_status(my_ros1_system::GetRobotStatus::Request &req,
                                        my_ros1_system::GetRobotStatus::Response &res)
{
    res.status = "Robot is active";
    res.battery_level = 75.5;
    return true;
}

void RobotNode::request_calculate_square(int number)
{
    my_ros1_system::CalculateSquare srv;
    srv.request.number = number;

    if (calculate_square_client_.call(srv))
    {
        ROS_INFO("Calculated square: %d", srv.response.square);
    }
    else
    {
        ROS_ERROR("Failed to call service calculate_square");
    }
}
```

---

# **📌 8️⃣ `main.cpp`**
```cpp
#include "ros/ros.h"
#include "robot_node.hpp"

int main(int argc, char **argv)
{
    ros::init(argc, argv, "robot_node");

    RobotNode node;

    ros::Rate loop_rate(1);
    while (ros::ok())
    {
        node.publish_status();
        node.publish_battery();
        ros::spinOnce();
        loop_rate.sleep();
    }

    return 0;
}
```

---

# **📌 9️⃣ 빌드 및 실행**
```sh
cd ~/catkin_ws
catkin_make
```

---

## **1️⃣ 실행**
```sh
roscore
rosrun my_ros1_system robot_node
```

---

이제 ROS1에서도 ROS2와 동일한 구조로 실행할 수 있습니다! 🚀😃
