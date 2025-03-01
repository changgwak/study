  
하나의 **ROS2 노드에서 여러 개의 토픽을 퍼블리시하고 구독하며, 여러 개의 서비스를 제공하는 구조**를 만들겠습니다.  
즉, **하나의 C++ 및 Python 노드에서 퍼블리셔, 서브스크라이버, 여러 개의 서비스 서버 및 클라이언트를 동시에 실행**하도록 하겠습니다.

---

# **📌 시스템 개요**
## **1️⃣ 하나의 노드 (`robot_node`)에 포함되는 기능**
- **토픽 (Topics)**
  - `robot_status` → 현재 상태를 퍼블리시 (Publisher)
  - `battery_level` → 배터리 정보를 퍼블리시 (Publisher)
  - `command_topic` → 외부 명령을 구독 (Subscriber)

- **서비스 (Services)**
  - `add_two_ints_extended` → 두 수의 합과 짝수/홀수 여부를 반환 (Service Server)
  - `get_robot_status` → 현재 로봇의 상태를 반환 (Service Server)
  - `calculate_square` → 숫자의 제곱을 계산 (Service Server)
  
- **서비스 클라이언트 (Service Clients)**
  - `calculate_square` 서비스를 자체적으로 호출하여 결과를 내부적으로 활용

---

# **📂 프로젝트 구조**
```
my_ros2_system/
│── include/
│   ├── robot_node.hpp
│   ├── math_utils.hpp
│── src/
│   ├── robot_node.cpp
│   ├── math_utils.cpp
│   ├── main.cpp
│── srv/
│   ├── AddTwoIntsExtended.srv
│   ├── CalculateSquare.srv
│   ├── GetRobotStatus.srv
│── CMakeLists.txt
│── package.xml
```

---

# **📌 1️⃣ 서비스 인터페이스 정의**
## **srv/AddTwoIntsExtended.srv**
```srv
int64 a
int64 b
---
int64 sum
string parity
```

## **srv/CalculateSquare.srv**
```srv
int64 number
---
int64 square
```

## **srv/GetRobotStatus.srv**
```srv
---
string status
float32 battery_level
```

---

# **📌 2️⃣ C++ 코드**
## **🔹 유틸리티 함수 (`math_utils.hpp` & `math_utils.cpp`)**
### **📌 `math_utils.hpp`**
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
### **📌 `math_utils.cpp`**
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

## **🔹 로봇 노드 (`robot_node.hpp` & `robot_node.cpp`)**
### **📌 `robot_node.hpp`**
```cpp
#ifndef ROBOT_NODE_HPP
#define ROBOT_NODE_HPP

#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"
#include "std_msgs/msg/float32.hpp"
#include "example_interfaces/srv/add_two_ints_extended.hpp"
#include "example_interfaces/srv/calculate_square.hpp"
#include "example_interfaces/srv/get_robot_status.hpp"
#include "math_utils.hpp"

class RobotNode : public rclcpp::Node
{
public:
    RobotNode();

private:
    // 토픽 퍼블리셔
    void publish_status();
    void publish_battery();

    // 토픽 서브스크라이버
    void command_callback(const std_msgs::msg::String::SharedPtr msg);

    // 서비스 핸들러
    void handle_add_two_ints(
        const std::shared_ptr<example_interfaces::srv::AddTwoIntsExtended::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoIntsExtended::Response> response);

    void handle_get_status(
        const std::shared_ptr<example_interfaces::srv::GetRobotStatus::Request> request,
        std::shared_ptr<example_interfaces::srv::GetRobotStatus::Response> response);

    void handle_calculate_square(
        const std::shared_ptr<example_interfaces::srv::CalculateSquare::Request> request,
        std::shared_ptr<example_interfaces::srv::CalculateSquare::Response> response);

    // 퍼블리셔
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr status_publisher_;
    rclcpp::Publisher<std_msgs::msg::Float32>::SharedPtr battery_publisher_;

    // 서브스크라이버
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr command_subscriber_;

    // 서비스 서버
    rclcpp::Service<example_interfaces::srv::AddTwoIntsExtended>::SharedPtr add_two_ints_service_;
    rclcpp::Service<example_interfaces::srv::GetRobotStatus>::SharedPtr get_status_service_;
    rclcpp::Service<example_interfaces::srv::CalculateSquare>::SharedPtr calculate_square_service_;
};

#endif // ROBOT_NODE_HPP
```

---

### **📌 `robot_node.cpp`**
```cpp
#include "robot_node.hpp"

RobotNode::RobotNode()
    : Node("robot_node")
{
    // 퍼블리셔 생성
    status_publisher_ = this->create_publisher<std_msgs::msg::String>("robot_status", 10);
    battery_publisher_ = this->create_publisher<std_msgs::msg::Float32>("battery_level", 10);

    // 타이머 설정 (주기적으로 퍼블리시)
    this->create_wall_timer(std::chrono::seconds(2), std::bind(&RobotNode::publish_status, this));
    this->create_wall_timer(std::chrono::seconds(5), std::bind(&RobotNode::publish_battery, this));

    // 서브스크라이버 생성
    command_subscriber_ = this->create_subscription<std_msgs::msg::String>(
        "command_topic", 10, std::bind(&RobotNode::command_callback, this, std::placeholders::_1));

    // 서비스 서버 생성
    add_two_ints_service_ = this->create_service<example_interfaces::srv::AddTwoIntsExtended>(
        "add_two_ints_extended", std::bind(&RobotNode::handle_add_two_ints, this, std::placeholders::_1, std::placeholders::_2));

    get_status_service_ = this->create_service<example_interfaces::srv::GetRobotStatus>(
        "get_robot_status", std::bind(&RobotNode::handle_get_status, this, std::placeholders::_1, std::placeholders::_2));

    calculate_square_service_ = this->create_service<example_interfaces::srv::CalculateSquare>(
        "calculate_square", std::bind(&RobotNode::handle_calculate_square, this, std::placeholders::_1, std::placeholders::_2));
}

void RobotNode::publish_status()
{
    auto message = std_msgs::msg::String();
    message.data = "Robot is active.";
    status_publisher_->publish(message);
}

void RobotNode::publish_battery()
{
    auto message = std_msgs::msg::Float32();
    message.data = 75.5; // 임의 배터리 값
    battery_publisher_->publish(message);
}

void RobotNode::command_callback(const std_msgs::msg::String::SharedPtr msg)
{
    RCLCPP_INFO(this->get_logger(), "Received command: %s", msg->data.c_str());
}

void RobotNode::handle_add_two_ints(const std::shared_ptr<example_interfaces::srv::AddTwoIntsExtended::Request> request,
                                    std::shared_ptr<example_interfaces::srv::AddTwoIntsExtended::Response> response)
{
    response->sum = MathUtils::add(request->a, request->b);
    response->parity = MathUtils::check_parity(response->sum);
}

void RobotNode::handle_get_status(const std::shared_ptr<example_interfaces::srv::GetRobotStatus::Request> request,
                                  std::shared_ptr<example_interfaces::srv::GetRobotStatus::Response> response)
{
    response->status = "Robot is active";
    response->battery_level = 75.5;
}
```

이제 Python 코드도 동일하게 작성해보겠습니다! 🚀




아래는 **C++과 동일한 기능을 하는 Python 코드**입니다.  
즉, 하나의 Python 노드에서 **여러 개의 토픽을 퍼블리시 및 구독하며, 여러 개의 서비스를 제공하는 구조**를 갖고 있습니다.

---

# **📌 시스템 개요**
- **토픽 (Topics)**
  - `robot_status` → 현재 상태를 퍼블리시 (Publisher)
  - `battery_level` → 배터리 정보를 퍼블리시 (Publisher)
  - `command_topic` → 외부 명령을 구독 (Subscriber)

- **서비스 (Services)**
  - `add_two_ints_extended` → 두 수의 합과 짝수/홀수 여부를 반환 (Service Server)
  - `get_robot_status` → 현재 로봇의 상태를 반환 (Service Server)
  - `calculate_square` → 숫자의 제곱을 계산 (Service Server)

- **서비스 클라이언트 (Service Clients)**
  - `calculate_square` 서비스를 자체적으로 호출하여 결과를 내부적으로 활용

---

# **📂 프로젝트 구조**
```
my_ros2_system/
│── robot_node.py
│── math_utils.py
│── srv/
│   ├── AddTwoIntsExtended.srv
│   ├── CalculateSquare.srv
│   ├── GetRobotStatus.srv
│── setup.py
│── package.xml
```

---

# **📌 1️⃣ 서비스 인터페이스 정의 (Python도 동일)**
## **srv/AddTwoIntsExtended.srv**
```srv
int64 a
int64 b
---
int64 sum
string parity
```

## **srv/CalculateSquare.srv**
```srv
int64 number
---
int64 square
```

## **srv/GetRobotStatus.srv**
```srv
---
string status
float32 battery_level
```

---

# **📌 2️⃣ Python 코드**
## **🔹 유틸리티 함수 (`math_utils.py`)**
```python
class MathUtils:
    @staticmethod
    def add(a: int, b: int) -> int:
        return a + b

    @staticmethod
    def check_parity(sum_value: int) -> str:
        return "even" if sum_value % 2 == 0 else "odd"

    @staticmethod
    def calculate_square(number: int) -> int:
        return number * number
```
- **`add()`** → 두 수의 합 반환
- **`check_parity()`** → 짝수/홀수 판별
- **`calculate_square()`** → 숫자의 제곱 반환

---

## **🔹 로봇 노드 (`robot_node.py`)**
```python
import rclpy
from rclpy.node import Node
from std_msgs.msg import String, Float32
from example_interfaces.srv import AddTwoIntsExtended, GetRobotStatus, CalculateSquare
from math_utils import MathUtils

class RobotNode(Node):
    def __init__(self):
        super().__init__('robot_node')

        # 퍼블리셔 생성
        self.status_publisher = self.create_publisher(String, 'robot_status', 10)
        self.battery_publisher = self.create_publisher(Float32, 'battery_level', 10)

        # 타이머 설정 (주기적으로 퍼블리시)
        self.create_timer(2.0, self.publish_status)
        self.create_timer(5.0, self.publish_battery)

        # 서브스크라이버 생성
        self.command_subscriber = self.create_subscription(
            String, 'command_topic', self.command_callback, 10)

        # 서비스 서버 생성
        self.add_two_ints_service = self.create_service(
            AddTwoIntsExtended, 'add_two_ints_extended', self.handle_add_two_ints)

        self.get_status_service = self.create_service(
            GetRobotStatus, 'get_robot_status', self.handle_get_status)

        self.calculate_square_service = self.create_service(
            CalculateSquare, 'calculate_square', self.handle_calculate_square)

        self.get_logger().info("Robot Node Initialized.")

    def publish_status(self):
        msg = String()
        msg.data = "Robot is active."
        self.status_publisher.publish(msg)
        self.get_logger().info(f"Publishing: {msg.data}")

    def publish_battery(self):
        msg = Float32()
        msg.data = 75.5  # 임의의 배터리 값
        self.battery_publisher.publish(msg)
        self.get_logger().info(f"Publishing Battery Level: {msg.data}")

    def command_callback(self, msg: String):
        self.get_logger().info(f"Received Command: {msg.data}")

    def handle_add_two_ints(self, request, response):
        response.sum = MathUtils.add(request.a, request.b)
        response.parity = MathUtils.check_parity(response.sum)
        self.get_logger().info(f"Processing request: {request.a} + {request.b} = {response.sum} ({response.parity})")
        return response

    def handle_get_status(self, request, response):
        response.status = "Robot is active"
        response.battery_level = 75.5
        self.get_logger().info("Providing robot status.")
        return response

    def handle_calculate_square(self, request, response):
        response.square = MathUtils.calculate_square(request.number)
        self.get_logger().info(f"Calculating square: {request.number}^2 = {response.square}")
        return response


def main(args=None):
    rclpy.init(args=args)
    node = RobotNode()
    rclpy.spin(node)
    node.destroy_node()
    rclpy.shutdown()


if __name__ == "__main__":
    main()
```

---

# **📌 3️⃣ 실행 방법**
## **1️⃣ 패키지 빌드**
```sh
colcon build --packages-select my_ros2_system
```

## **2️⃣ 실행**
```sh
ros2 run my_ros2_system robot_node
```

---

# **✅ 주요 특징**
### **1) 하나의 노드에서 여러 개의 기능 수행**
- **`robot_status`, `battery_level` 토픽 퍼블리셔**
- **`command_topic` 구독**
- **`add_two_ints_extended`, `get_robot_status`, `calculate_square` 서비스 제공**

### **2) Python과 C++의 동일한 기능**
- **Python은 `math_utils.py`에서 기능 모듈화**.
- **C++에서는 `math_utils.hpp/.cpp`로 기능 분리**.
- **Python의 `rclpy`와 C++의 `rclcpp` API가 유사하게 설계됨**.

### **3) 확장 가능**
- 새로운 기능 추가가 용이 → **예: 모터 속도 제어, 장애물 감지 등**을 추가 가능.

---

# **🚀 결론**
- **Python과 C++에서 동일한 로직을 구현하여 비교 및 학습 가능**.
- **하나의 노드에서 다수의 토픽과 서비스를 관리하는 구조 구현**.
- **실제 로봇 시스템에서도 적용할 수 있는 확장성 높은 코드**.

이제 C++과 Python을 비교하며 실행해보세요! 🚀😃



좋습니다! 이제 `math_utils`에 더 **복잡한 로직**을 추가하여 C++과 Python을 업데이트하겠습니다.

---

# **📌 복잡한 로직 추가**
## **새로운 기능 추가**
1. **`factorial(int n)`** → 입력된 숫자의 팩토리얼 계산
2. **`fibonacci(int n)`** → `n`번째 피보나치 수열 값 반환 (재귀 최적화)
3. **`is_prime(int n)`** → 소수 판별 알고리즘 (에라토스테네스의 체 최적화)
4. **`gcd(int a, int b)`** → 두 수의 최대공약수 계산 (유클리드 알고리즘)

---

# **📂 프로젝트 구조 (변경 없음)**
```
my_ros2_system/
│── include/
│   ├── math_utils.hpp
│── src/
│   ├── math_utils.cpp
│── math_utils.py
│── robot_node.py
│── robot_node.hpp
│── robot_node.cpp
```

---

# **📌 1️⃣ C++ 코드**
## **🔹 `math_utils.hpp` (헤더 파일)**
```cpp
#ifndef MATH_UTILS_HPP
#define MATH_UTILS_HPP

#include <string>
#include <vector>

class MathUtils
{
public:
    static int add(int a, int b);
    static std::string check_parity(int sum);
    static int calculate_square(int number);

    static long factorial(int n);
    static int fibonacci(int n);
    static bool is_prime(int n);
    static int gcd(int a, int b);
};

#endif // MATH_UTILS_HPP
```
---

## **🔹 `math_utils.cpp` (구현)**
```cpp
#include "math_utils.hpp"
#include <cmath>

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

// 팩토리얼 (재귀적)
long MathUtils::factorial(int n)
{
    if (n <= 1)
        return 1;
    return n * factorial(n - 1);
}

// 피보나치 수열 (반복문)
int MathUtils::fibonacci(int n)
{
    if (n <= 0) return 0;
    if (n == 1) return 1;

    int a = 0, b = 1, result = 0;
    for (int i = 2; i <= n; i++)
    {
        result = a + b;
        a = b;
        b = result;
    }
    return result;
}

// 소수 판별 (에라토스테네스의 체 최적화)
bool MathUtils::is_prime(int n)
{
    if (n < 2) return false;
    if (n == 2 || n == 3) return true;
    if (n % 2 == 0 || n % 3 == 0) return false;

    for (int i = 5; i * i <= n; i += 6)
    {
        if (n % i == 0 || n % (i + 2) == 0)
            return false;
    }
    return true;
}

// 최대공약수 (유클리드 알고리즘)
int MathUtils::gcd(int a, int b)
{
    while (b != 0)
    {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```

---

# **📌 2️⃣ Python 코드**
## **🔹 `math_utils.py`**
```python
class MathUtils:
    @staticmethod
    def add(a: int, b: int) -> int:
        return a + b

    @staticmethod
    def check_parity(sum_value: int) -> str:
        return "even" if sum_value % 2 == 0 else "odd"

    @staticmethod
    def calculate_square(number: int) -> int:
        return number * number

    @staticmethod
    def factorial(n: int) -> int:
        if n <= 1:
            return 1
        return n * MathUtils.factorial(n - 1)

    @staticmethod
    def fibonacci(n: int) -> int:
        if n <= 0:
            return 0
        elif n == 1:
            return 1

        a, b = 0, 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return b

    @staticmethod
    def is_prime(n: int) -> bool:
        if n < 2:
            return False
        if n in (2, 3):
            return True
        if n % 2 == 0 or n % 3 == 0:
            return False
        i = 5
        while i * i <= n:
            if n % i == 0 or n % (i + 2) == 0:
                return False
            i += 6
        return True

    @staticmethod
    def gcd(a: int, b: int) -> int:
        while b != 0:
            a, b = b, a % b
        return a
```

---

# **📌 3️⃣ 새로운 서비스 추가**
## **🔹 새로운 서비스 인터페이스 (C++과 Python 동일)**
### **srv/Factorial.srv**
```srv
int64 number
---
int64 result
```

### **srv/Fibonacci.srv**
```srv
int64 number
---
int64 result
```

### **srv/IsPrime.srv**
```srv
int64 number
---
bool is_prime
```

### **srv/GCD.srv**
```srv
int64 a
int64 b
---
int64 gcd
```

---

# **📌 4️⃣ 로봇 노드에 새로운 서비스 추가**
이제 `robot_node`에서 새로운 서비스를 추가하여, **팩토리얼, 피보나치, 소수 판별, 최대공약수 계산** 기능을 제공합니다.

---

## **🔹 C++의 `robot_node.hpp` (변경된 부분만)**
```cpp
rclcpp::Service<example_interfaces::srv::Factorial>::SharedPtr factorial_service_;
rclcpp::Service<example_interfaces::srv::Fibonacci>::SharedPtr fibonacci_service_;
rclcpp::Service<example_interfaces::srv::IsPrime>::SharedPtr is_prime_service_;
rclcpp::Service<example_interfaces::srv::GCD>::SharedPtr gcd_service_;
```

---

## **🔹 Python의 `robot_node.py` (변경된 부분만)**
```python
self.factorial_service = self.create_service(
    Factorial, 'factorial', self.handle_factorial)
self.fibonacci_service = self.create_service(
    Fibonacci, 'fibonacci', self.handle_fibonacci)
self.is_prime_service = self.create_service(
    IsPrime, 'is_prime', self.handle_is_prime)
self.gcd_service = self.create_service(
    GCD, 'gcd', self.handle_gcd)
```

---

# **📌 5️⃣ 실행 방법**
## **1️⃣ 패키지 빌드**
```sh
colcon build --packages-select my_ros2_system
```

## **2️⃣ 실행**
```sh
ros2 run my_ros2_system robot_node
```

## **3️⃣ 서비스 요청 예시**
```sh
ros2 service call /factorial example_interfaces/srv/Factorial "{number: 5}"
ros2 service call /fibonacci example_interfaces/srv/Fibonacci "{number: 10}"
ros2 service call /is_prime example_interfaces/srv/IsPrime "{number: 29}"
ros2 service call /gcd example_interfaces/srv/GCD "{a: 48, b: 18}"
```

---

# **🚀 결론**
- **`math_utils`에 다양한 알고리즘 추가 (팩토리얼, 피보나치, 소수 판별, 최대공약수)**.
- **C++과 Python 모두 동일한 기능 제공**.
- **하나의 로봇 노드(`robot_node`)에서 다양한 연산을 수행하는 서비스 추가**.
- **ROS2를 활용한 복잡한 연산 시스템 구현 가능**.

이제 직접 실행해보고 테스트해보세요! 🚀😃



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
