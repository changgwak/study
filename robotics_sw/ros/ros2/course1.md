여기 C++ 프로그래밍과 ROS2를 결합한 강좌의 전체적인 목차를 제안합니다. 초급자부터 중급, 고급까지 점진적으로 학습할 수 있도록 구성했습니다.

---

## **C++ 프로그래밍과 ROS2 개발 강좌 목차**

### **1. ROS2와 C++ 개요**
- ROS2란 무엇인가? (기본 개념 및 아키텍처 소개)
- ROS1과 ROS2의 차이점
- ROS2에서 C++의 역할
- C++ 표준 (C++11, C++14, C++17) 및 ROS2에서의 적용

---

## **2. C++ 기초 문법 (ROS2 적용을 위한 필수 개념)**
- C++ 프로그램 구조 및 빌드 시스템 (CMake 소개)
- 변수, 데이터 타입, 연산자
- 조건문과 반복문
- 함수 및 매개변수 전달 방식 (값, 참조, 포인터)

---

## **3. 객체지향 프로그래밍 (OOP)과 ROS2 적용**
- 클래스와 객체
- 생성자와 소멸자
- 접근 지정자 (public, private, protected)
- 상속과 다형성 (virtual, override, final 키워드)
- 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`) - ROS2에서 자주 사용됨
- `std::weak_ptr`와 `std::make_shared`의 활용

---

## **4. C++ STL과 ROS2에서의 활용**
- 벡터 (`std::vector`) - ROS2 메시지 데이터 저장 활용
- 리스트 (`std::list`), 맵 (`std::map`), 셋 (`std::set`) 활용
- 문자열 처리 (`std::string`, `std::stringstream`)
- 람다 함수와 `std::function` - ROS2 콜백 처리 시 필수

---

## **5. C++ 멀티스레딩과 병렬 프로그래밍 (ROS2에서의 활용)**
- C++ 스레드 (`std::thread`, `std::mutex`, `std::condition_variable`)
- `std::async`와 `std::future`를 활용한 비동기 프로그래밍
- ROS2 Executor와 멀티스레딩 전략
- ROS2에서 `rclcpp::executors::MultiThreadedExecutor` 사용법

---

## **6. ROS2 C++ 환경 설정 및 패키지 빌드**
- ROS2 개발 환경 설치 (Ubuntu + ROS2 Humble/Foxy)
- C++ 기반 ROS2 패키지 생성 (`ament_cmake`)
- `colcon` 빌드 시스템 소개 및 빌드 방법
- C++ 코드 스타일 가이드 (`ament_lint`, `clang-format`)

---

## **7. ROS2 노드(Node) 프로그래밍**
- `rclcpp::Node` 클래스를 활용한 기본 노드 생성
- ROS2 패키지에서 C++ 노드 실행하기 (`ros2 run`)
- 노드의 라이프사이클 (`LifecycleNode`)

---

## **8. ROS2 통신 기초 (C++ 적용)**
- 토픽 (Topic) 기반 통신
  - 퍼블리셔 (`rclcpp::Publisher`)
  - 서브스크라이버 (`rclcpp::Subscription`)
  - QoS 설정 (`rclcpp::QoS`)
- 서비스 (Service) 통신
  - 서비스 서버 (`rclcpp::Service`)
  - 서비스 클라이언트 (`rclcpp::Client`)
- 액션 (Action) 기반 통신 (`rclcpp_action`)
  - 액션 서버와 액션 클라이언트 구현

---

## **9. ROS2 메시지 타입과 C++에서의 활용**
- 기본 메시지 타입 (`std_msgs`, `sensor_msgs`, `geometry_msgs`)
- 커스텀 메시지 생성 (`rosidl_generator_cpp`)
- 메시지 직렬화 및 역직렬화 (`rclcpp::Serialization`)

---

## **10. ROS2 TF2와 C++**
- `tf2_ros::Buffer`와 `tf2_ros::TransformListener` 사용법
- 좌표 변환 및 프레임 관리 (`geometry_msgs::TransformStamped`)
- C++을 활용한 TF 브로드캐스트 및 리스너 구현

---

## **11. ROS2 파라미터 서버 및 C++에서의 활용**
- `rclcpp::Parameter`와 파라미터 선언
- 동적 파라미터 업데이트 (`rclcpp::ParameterEventHandler`)

---

## **12. ROS2 로깅 및 디버깅**
- ROS2에서 로깅 (`RCLCPP_INFO`, `RCLCPP_DEBUG`, `RCLCPP_WARN`, `RCLCPP_ERROR`)
- `ros2 bag`을 활용한 데이터 기록 및 재생
- `gdb`와 `valgrind`를 이용한 C++ 디버깅

---

## **13. ROS2 파일 I/O 및 데이터 처리**
- `std::fstream`을 활용한 파일 입출력
- CSV, JSON, YAML 파일 처리 (`yaml-cpp` 활용)

---

## **14. ROS2 플러그인과 C++ 인터페이스**
- ROS2 플러그인 (`pluginlib`)
- C++ 기반 ROS2 인터페이스 (`rclcpp::NodeInterfaces`)

---

## **15. ROS2 네비게이션과 SLAM C++ 적용**
- ROS2 Navigation2 개요 (`nav2_bringup`, `nav2_lifecycle_manager`)
- SLAM Toolbox와 Cartographer SLAM을 C++ 코드로 제어
- ROS2에서 C++로 경로 계획 (`nav_msgs::Path`)

---

## **16. ROS2에서 C++로 AI 및 컴퓨터 비전 적용**
- OpenCV를 활용한 이미지 처리 (`cv_bridge`)
- YOLO 및 딥러닝 모델을 ROS2 C++에서 실행 (`ONNX Runtime`)
- `rclcpp::Subscription<ImageMsg>` 활용한 이미지 스트림 처리

---

## **17. 최적화 및 배포**
- 성능 최적화 (`rclcpp::Timer` 활용)
- 크로스 컴파일 및 경량화 (`ros2 cross_compile`)
- Docker를 활용한 배포 (`Dockerfile`, `ros_entrypoint.sh`)

---

이 강좌는 ROS2를 활용한 실전 C++ 프로그래밍을 목표로 하며, 기초부터 고급까지 체계적으로 학습할 수 있도록 구성되었습니다. 추가적으로 원하는 내용이 있다면 알려주세요! 🚀


<br>
<br>
<br>
<br>
## **1. ROS2와 C++ 개요**

### **ROS2란 무엇인가? (기본 개념 및 아키텍처 소개)**  
ROS2 (Robot Operating System 2)는 로봇 개발을 위한 오픈 소스 프레임워크로, 분산 시스템을 활용하여 여러 노드(Node) 간의 통신을 쉽게 할 수 있도록 지원합니다. ROS1의 단점을 개선하여, **실시간성, 분산 시스템, 다양한 OS 지원, 보안성** 등을 강화한 버전입니다.

#### **ROS2 아키텍처 개요**  
ROS2는 퍼블리셔-서브스크라이버(Pub-Sub) 모델을 기반으로 하며, 주요 요소는 다음과 같습니다.

1. **노드(Node)**: 개별적인 실행 단위. 예를 들어, 카메라 데이터 수집 노드와 이미지 처리 노드는 각각 별도의 노드로 실행됨.
2. **토픽(Topic)**: 노드 간 메시지를 주고받는 채널. 퍼블리셔(Publisher)가 데이터를 송신하고, 서브스크라이버(Subscriber)가 데이터를 수신함.
3. **서비스(Service)**: 요청(Request)과 응답(Response) 방식의 통신을 제공하는 RPC 모델.
4. **액션(Action)**: 목표 설정 후 진행 상태를 모니터링하며 실행하는 기능 (예: 로봇 팔의 이동).
5. **파라미터(Parameter)**: 노드의 설정값을 저장하고 관리하는 기능.
6. **tf2 (Transform Library)**: 로봇의 좌표 변환을 담당하는 라이브러리.
7. **Executors (실행자)**: ROS2의 멀티스레딩 및 태스크 관리를 담당하는 구조.

🔹 **예제: ROS2에서 기본 노드 실행**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "Hello ROS2!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();
    return 0;
}
```
💡 위 코드는 ROS2에서 "my_node"라는 이름을 가진 노드를 생성하고 실행하는 기본 코드입니다.

---

### **ROS1과 ROS2의 차이점**
| 기능 | ROS1 | ROS2 |
|------|------|------|
| 통신 미들웨어 | ROS 자체 메시지 전달 시스템 | DDS(Data Distribution Service) 사용 |
| 실시간 지원 | 없음 | RTOS(실시간 운영체제) 지원 |
| 멀티 플랫폼 | 주로 Ubuntu 지원 | Windows, MacOS, RTOS 등 다양한 플랫폼 지원 |
| 멀티스레딩 | 노드당 하나의 스레드 | Executor를 통해 멀티스레드 지원 |
| 보안성 | 없음 | DDS의 보안 기능 활용 가능 |
| 네트워크 설정 | ROS Master 필요 | Master 없이 분산 네트워크 사용 가능 |

🔹 **ROS1과 ROS2 통신 방식 비교 예제**
```cpp
// ROS1 - Master 기반 (Python 예제)
// Publisher
import rospy
from std_msgs.msg import String

rospy.init_node('talker')
pub = rospy.Publisher('/chatter', String, queue_size=10)

while not rospy.is_shutdown():
    pub.publish("Hello from ROS1")

// ROS2 - DDS 기반 (C++ 예제)
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class Talker : public rclcpp::Node {
public:
    Talker() : Node("talker") {
        publisher_ = this->create_publisher<std_msgs::msg::String>("/chatter", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
                [this]() {
                    auto msg = std_msgs::msg::String();
                    msg.data = "Hello from ROS2";
                    publisher_->publish(msg);
                });
    }
private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<Talker>());
    rclcpp::shutdown();
    return 0;
}
```
💡 ROS2는 ROS Master 없이 DDS를 활용해 네트워크 분산 통신을 수행합니다.

---

### **ROS2에서 C++의 역할**
ROS2는 C++과 Python을 지원하지만, **고성능, 실시간 시스템, 멀티스레딩 제어**를 위해 C++이 주요 언어로 사용됩니다.

#### **C++의 주요 역할**
1. **노드 작성**: `rclcpp` 라이브러리를 사용하여 노드 생성
2. **토픽 퍼블리셔/서브스크라이버**: 센서 데이터 수집 및 처리
3. **서비스 및 액션 서버**: 로봇의 특정 기능 제어
4. **멀티스레드 및 병렬 처리**: `rclcpp::executors::MultiThreadedExecutor`를 활용한 고속 데이터 처리
5. **메모리 관리 최적화**: `std::shared_ptr`, `std::unique_ptr` 활용

🔹 **C++ 기반 퍼블리셔 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<rclcpp::Node>("publisher_node");
    auto publisher = node->create_publisher<std_msgs::msg::String>("chatter", 10);

    rclcpp::Rate loop_rate(1);
    while (rclcpp::ok()) {
        auto msg = std_msgs::msg::String();
        msg.data = "Hello from C++ ROS2!";
        publisher->publish(msg);
        loop_rate.sleep();
    }
    rclcpp::shutdown();
    return 0;
}
```
💡 위 코드는 1초 간격으로 문자열 메시지를 퍼블리싱하는 간단한 ROS2 C++ 노드입니다.

---

### **C++ 표준 (C++11, C++14, C++17) 및 ROS2에서의 적용**
ROS2는 기본적으로 C++17을 지원하며, 일부 기능은 C++14와 C++11을 기반으로 사용됩니다.

#### **ROS2에서 활용되는 주요 C++ 기능**
| C++ 표준 | 주요 기능 | ROS2에서의 적용 |
|----------|----------|----------------|
| C++11 | `std::shared_ptr`, `std::unique_ptr`, `std::bind` | 스마트 포인터 활용, 콜백 바인딩 |
| C++14 | `std::make_unique`, 제너릭 람다 | 스마트 포인터 최적화, 람다 활용 |
| C++17 | `std::optional`, `std::variant`, `if constexpr` | 파라미터 설정, 메시지 처리 최적화 |

🔹 **C++ 스마트 포인터 활용 예제**
```cpp
#include <memory>
#include "rclcpp/rclcpp.hpp"

class SmartPointerExample {
public:
    SmartPointerExample() {
        node_ = std::make_shared<rclcpp::Node>("smart_pointer_node");
    }
    void run() {
        RCLCPP_INFO(node_->get_logger(), "Smart Pointer Example Running");
    }
private:
    std::shared_ptr<rclcpp::Node> node_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto example = std::make_unique<SmartPointerExample>();
    example->run();
    rclcpp::shutdown();
    return 0;
}
```
💡 `std::shared_ptr`와 `std::make_unique`를 사용하여 메모리 관리를 자동화할 수 있습니다.

---

## **📌 정리**
- ROS2는 분산 네트워크를 기반으로 실시간, 멀티플랫폼, 보안성을 강화한 로봇 개발 프레임워크입니다.
- ROS1과 달리 DDS 기반 통신을 활용하며, Master 없이 노드 간 직접 통신이 가능합니다.
- C++은 ROS2에서 성능 최적화를 위해 필수적인 언어로 사용되며, 스마트 포인터, 멀티스레딩, 람다 함수 등이 적극 활용됩니다.
- C++11, C++14, C++17의 다양한 기능이 ROS2에서 효과적으로 사용됩니다.

이해가 쉽게 설명되었나요? 추가 설명이 필요하면 알려주세요! 🚀




<br>
<br>
<br>
<br>
<br>

## **2. C++ 기초 문법 (ROS2 적용을 위한 필수 개념)**

ROS2에서 C++을 사용할 때 기본적으로 알아야 할 개념들을 정리하고, ROS2와의 연관성을 설명하겠습니다.

---

### **1. C++ 프로그램 구조 및 빌드 시스템 (CMake 소개)**

#### **C++ 프로그램 기본 구조**
C++ 프로그램은 다음과 같은 기본 구조를 가집니다.

```cpp
#include <iostream>  // 표준 입출력 라이브러리

int main() {
    std::cout << "Hello, C++!" << std::endl;
    return 0;
}
```
💡 `std::cout`을 사용하여 콘솔에 출력을 수행하고, `return 0;`은 프로그램이 정상적으로 종료되었음을 나타냅니다.

---

#### **CMake를 이용한 빌드 시스템**
ROS2에서는 **CMake**를 사용하여 코드를 빌드합니다. 기본적인 `CMakeLists.txt` 파일을 만들고 컴파일하는 과정을 살펴보겠습니다.

🔹 **예제: CMake를 이용한 C++ 프로그램 빌드**
1. `main.cpp` 파일 작성:
```cpp
#include <iostream>

int main() {
    std::cout << "CMake를 이용한 C++ 프로그램 빌드!" << std::endl;
    return 0;
}
```
2. `CMakeLists.txt` 파일 작성:
```cmake
cmake_minimum_required(VERSION 3.5)
project(my_cpp_program)

add_executable(my_program main.cpp)
```
3. 빌드 및 실행:
```bash
mkdir build && cd build
cmake ..
make
./my_program
```
💡 ROS2에서도 `CMakeLists.txt`를 활용하여 패키지를 빌드합니다.

---

### **2. 변수, 데이터 타입, 연산자**

#### **기본 데이터 타입**
| 타입 | 설명 | 예제 |
|------|------|------|
| `int` | 정수형 데이터 | `int a = 10;` |
| `float` | 실수형 (소수점) | `float b = 3.14;` |
| `double` | 더 정밀한 실수형 | `double c = 3.14159;` |
| `char` | 한 개의 문자 | `char d = 'A';` |
| `bool` | 논리형 (참/거짓) | `bool is_ros2 = true;` |

🔹 **예제: 다양한 변수 선언**
```cpp
#include <iostream>

int main() {
    int a = 10;
    double pi = 3.14159;
    char letter = 'R';
    bool is_ros2 = true;

    std::cout << "정수: " << a << "\n";
    std::cout << "실수: " << pi << "\n";
    std::cout << "문자: " << letter << "\n";
    std::cout << "논리값: " << is_ros2 << "\n";

    return 0;
}
```

---

#### **연산자**
| 연산자 | 설명 | 예제 |
|------|------|------|
| `+`  | 덧셈 | `a + b` |
| `-`  | 뺄셈 | `a - b` |
| `*`  | 곱셈 | `a * b` |
| `/`  | 나눗셈 | `a / b` |
| `%`  | 나머지 연산 | `a % b` |
| `==` | 같음 비교 | `a == b` |
| `!=` | 다름 비교 | `a != b` |
| `&&` | AND 연산 | `true && false` |
| `||` | OR 연산 | `true || false` |
| `!`  | NOT 연산 | `!true` |

🔹 **ROS2에서 연산자 활용 예제**
```cpp
#include <iostream>
#include "rclcpp/rclcpp.hpp"

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<rclcpp::Node>("operator_example");

    int a = 10, b = 5;
    RCLCPP_INFO(node->get_logger(), "a + b = %d", a + b);
    RCLCPP_INFO(node->get_logger(), "a * b = %d", a * b);
    RCLCPP_INFO(node->get_logger(), "a > b ? %s", (a > b ? "true" : "false"));

    rclcpp::shutdown();
    return 0;
}
```
💡 `RCLCPP_INFO()`를 사용하면 ROS2의 로그 시스템을 활용할 수 있습니다.

---

### **3. 조건문과 반복문**

#### **조건문 (if, switch)**
🔹 **예제: ROS2에서 if문 활용**
```cpp
#include "rclcpp/rclcpp.hpp"

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<rclcpp::Node>("if_example");

    int speed = 30;
    if (speed > 20) {
        RCLCPP_INFO(node->get_logger(), "속도가 너무 빠릅니다!");
    } else {
        RCLCPP_INFO(node->get_logger(), "안전한 속도입니다.");
    }

    rclcpp::shutdown();
    return 0;
}
```

---

#### **반복문 (for, while, do-while)**
🔹 **예제: for문을 이용한 반복 실행**
```cpp
#include "rclcpp/rclcpp.hpp"

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<rclcpp::Node>("for_example");

    for (int i = 0; i < 5; i++) {
        RCLCPP_INFO(node->get_logger(), "반복 실행 중: %d", i);
    }

    rclcpp::shutdown();
    return 0;
}
```
💡 for문은 특정 횟수만큼 반복할 때 사용됩니다.

---

### **4. 함수 및 매개변수 전달 방식 (값, 참조, 포인터)**

#### **함수 정의 및 호출**
```cpp
#include <iostream>

void printMessage() {
    std::cout << "Hello, ROS2!" << std::endl;
}

int main() {
    printMessage();
    return 0;
}
```

---

#### **매개변수 전달 방식**
| 방식 | 설명 | 예제 |
|------|------|------|
| 값 전달 | 복사본을 전달하여 원본에 영향을 주지 않음 | `void func(int x)` |
| 참조 전달 | 원본을 직접 참조하여 수정 가능 | `void func(int &x)` |
| 포인터 전달 | 메모리 주소를 전달하여 원본 수정 가능 | `void func(int *x)` |

🔹 **예제: 값 전달 vs 참조 전달 vs 포인터 전달**
```cpp
#include <iostream>

// 값 전달
void byValue(int x) {
    x = 20;
}

// 참조 전달
void byReference(int &x) {
    x = 20;
}

// 포인터 전달
void byPointer(int *x) {
    *x = 20;
}

int main() {
    int a = 10;
    byValue(a);
    std::cout << "값 전달 후 a: " << a << std::endl; // 10 (변화 없음)

    byReference(a);
    std::cout << "참조 전달 후 a: " << a << std::endl; // 20 (변화됨)

    a = 10;
    byPointer(&a);
    std::cout << "포인터 전달 후 a: " << a << std::endl; // 20 (변화됨)

    return 0;
}
```
💡 참조와 포인터는 ROS2에서 노드 객체를 다룰 때 자주 사용됩니다.

---

### **📌 정리**
- C++ 기본 문법과 ROS2 적용 사례를 연계하여 학습해야 함.
- CMake를 사용해 C++ 프로그램을 빌드하고, ROS2의 `CMakeLists.txt`와 연관됨.
- 변수, 연산자, 조건문, 반복문, 함수 개념을 이해하고 ROS2 코드에서 활용 가능.

추가 설명이 필요하면 언제든지 알려주세요! 🚀

<br>
<br>
<br>
## **ROS2에서의 레퍼런스(Reference)와 포인터(Pointer)**

C++에서 **레퍼런스(Reference)와 포인터(Pointer)** 는 메모리를 효율적으로 관리하고 데이터의 주소를 다룰 수 있도록 도와주는 중요한 개념입니다.  
ROS2에서는 **스마트 포인터(std::shared_ptr, std::unique_ptr)** 와 **레퍼런스** 를 많이 활용하며, 노드, 메시지, 콜백 함수 등에서 중요한 역할을 합니다.

---

## **1. 레퍼런스(Reference)란?**
레퍼런스는 기존 변수를 가리키는 또 다른 이름(alias)이며, **주소값을 직접 다룰 필요 없이 원본 변수의 내용을 수정**할 수 있습니다.  
레퍼런스는 `&` 연산자를 사용하여 선언하며, **초기화 이후 다른 변수에 재할당할 수 없습니다.**

🔹 **기본적인 레퍼런스 사용 예제**
```cpp
#include <iostream>

void modifyValue(int &ref) {
    ref += 10;
}

int main() {
    int num = 5;
    int &alias = num;  // num을 참조하는 레퍼런스

    alias = 10;  // num의 값이 변경됨
    std::cout << "num: " << num << std::endl; // 출력: 10

    modifyValue(num);
    std::cout << "num after modifyValue: " << num << std::endl; // 출력: 20

    return 0;
}
```
💡 레퍼런스를 사용하면 불필요한 복사 비용이 줄어들고, 원본 데이터를 직접 수정할 수 있습니다.

---

### **📌 ROS2에서 레퍼런스 활용 예제**
#### **1) 콜백 함수에서 메시지를 레퍼런스로 전달**
ROS2에서 메시지를 처리할 때, 레퍼런스를 사용하면 데이터를 복사하지 않고 빠르게 접근할 수 있습니다.

🔹 **ROS2에서 레퍼런스를 활용한 콜백 함수 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MinimalSubscriber : public rclcpp::Node {
public:
    MinimalSubscriber() : Node("minimal_subscriber") {
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "topic", 10, 
            std::bind(&MinimalSubscriber::topic_callback, this, std::placeholders::_1));
    }

private:
    void topic_callback(const std_msgs::msg::String::SharedPtr &msg) {  
        RCLCPP_INFO(this->get_logger(), "Received: '%s'", msg->data.c_str());
    }

    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MinimalSubscriber>());
    rclcpp::shutdown();
    return 0;
}
```
💡 `const std_msgs::msg::String::SharedPtr &msg`  
→ **레퍼런스를 사용하여 메시지를 복사하지 않고 직접 접근할 수 있도록 최적화!**

---

## **2. 포인터(Pointer)란?**
포인터는 **메모리 주소를 저장하는 변수** 입니다.  
C++에서는 `*` 연산자를 사용하여 포인터를 선언하며, 포인터를 이용하면 **동적 메모리 할당과 데이터 구조의 효율적인 관리**가 가능합니다.

🔹 **기본적인 포인터 사용 예제**
```cpp
#include <iostream>

void modifyValue(int *ptr) {
    *ptr += 10;
}

int main() {
    int num = 5;
    int *ptr = &num;  // num의 주소를 저장

    *ptr = 10;  // num의 값이 변경됨
    std::cout << "num: " << num << std::endl; // 출력: 10

    modifyValue(ptr);
    std::cout << "num after modifyValue: " << num << std::endl; // 출력: 20

    return 0;
}
```
💡 `ptr`이 `num`의 주소를 가리키므로, `*ptr`을 사용하여 num의 값을 직접 변경할 수 있습니다.

---

### **📌 ROS2에서 포인터 활용 예제**
#### **1) 스마트 포인터 (std::shared_ptr)**
ROS2에서는 **스마트 포인터(std::shared_ptr, std::unique_ptr)** 를 사용하여 메모리 관리를 자동화합니다.  
특히, **ROS2의 노드, 메시지, 퍼블리셔/서브스크라이버, 액션 서버 등에서 `std::shared_ptr`을 많이 사용합니다.**

🔹 **ROS2에서 `std::shared_ptr`을 활용한 퍼블리셔 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MinimalPublisher : public rclcpp::Node {
public:
    MinimalPublisher() : Node("minimal_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::String>("topic", 10);
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1), 
            std::bind(&MinimalPublisher::publish_message, this));
    }

private:
    void publish_message() {
        auto message = std::make_shared<std_msgs::msg::String>();
        message->data = "Hello, ROS2 with std::shared_ptr!";
        publisher_->publish(*message);  
    }

    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MinimalPublisher>());
    rclcpp::shutdown();
    return 0;
}
```
💡 `std::shared_ptr<std_msgs::msg::String>`을 사용하여 메시지를 동적 할당하여 퍼블리싱합니다.

---

#### **2) `std::unique_ptr` 사용 예제**
`std::unique_ptr`은 하나의 객체만 소유할 수 있으며, 자동으로 메모리를 해제합니다.

🔹 **ROS2에서 `std::unique_ptr` 활용**
```cpp
#include <memory>
#include "rclcpp/rclcpp.hpp"

class UniqueNode {
public:
    UniqueNode() {
        node_ = std::make_unique<rclcpp::Node>("unique_node");
        RCLCPP_INFO(node_->get_logger(), "UniqueNode Created!");
    }

private:
    std::unique_ptr<rclcpp::Node> node_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto unique_example = std::make_unique<UniqueNode>();
    rclcpp::shutdown();
    return 0;
}
```
💡 `std::unique_ptr`를 사용하면, 노드가 더 이상 필요 없을 때 자동으로 해제됩니다.

---

## **3. 레퍼런스 vs 포인터 비교**
| 항목 | 레퍼런스 (`&`) | 포인터 (`*`) |
|------|--------------|--------------|
| 메모리 주소 | 변수의 별칭 (Alias) | 변수의 주소를 저장 |
| NULL 값 | NULL이 될 수 없음 | NULL이 될 수 있음 |
| 변경 가능 여부 | 한 번 초기화 후 변경 불가 | 다른 변수를 가리킬 수 있음 |
| 사용 방식 | `int &ref = a;` | `int *ptr = &a;` |

🔹 **차이점 예제**
```cpp
int a = 10;
int &ref = a;  // 레퍼런스
int *ptr = &a; // 포인터

ref = 20;  // a의 값이 변경됨
*ptr = 30; // a의 값이 변경됨

std::cout << a << std::endl;  // 출력: 30
```
💡 **레퍼런스는 고정된 변수만 가리킬 수 있지만, 포인터는 동적으로 다른 주소를 가리킬 수 있습니다.**

---

## **📌 정리**
- **레퍼런스(`&`)** : 변수를 직접 가리키는 또 다른 이름, `const &`를 활용하면 복사 없이 읽기 가능.
- **포인터(`*`)** : 메모리 주소를 저장하는 변수, 동적 할당과 메모리 관리 가능.
- **ROS2에서 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)** 를 적극 활용하여 메모리 누수를 방지.
- **콜백 함수에서 메시지 전달 시 `const std::shared_ptr<T> &`를 사용하면 성능 최적화 가능.**

이해하기 쉬운 설명이었나요? 추가 질문이 있으면 알려주세요! 🚀

<br>
<br>
<br>
레퍼런스(`&`)와 포인터(`*`)는 **둘 다 변수의 주소를 활용하여 원본 데이터를 수정할 수 있지만**, 사용 방식과 동작이 다릅니다.  
핵심 차이를 더 명확히 이해할 수 있도록 **메모리 구조, 변경 가능성, 사용 사례, 안전성**을 중심으로 설명하겠습니다.

---

## **1. 레퍼런스와 포인터의 핵심 차이**

| 비교 항목 | 레퍼런스 (`&`) | 포인터 (`*`) |
|----------|--------------|--------------|
| **주소 저장 여부** | 변수의 **별칭(Alias)** 역할 (주소 저장 X) | 변수의 **주소를 저장** (주소 저장 O) |
| **NULL 가능 여부** | NULL을 가질 수 없음 (무조건 유효한 변수 가리켜야 함) | NULL 가능 (초기화하지 않으면 위험) |
| **초기화 이후 재할당** | **초기화된 변수만 사용 가능, 이후 변경 불가** | **다른 변수를 가리킬 수 있음 (재할당 가능)** |
| **사용 목적** | 변수의 또 다른 이름으로 활용, 간단한 사용법 | 동적 메모리 관리, 재할당이 필요한 경우 |
| **객체 크기** | 실제 데이터 크기와 동일 | **주소 크기(4바이트 또는 8바이트)** |

---

## **2. 메모리 구조 차이**
레퍼런스와 포인터의 가장 큰 차이는 **메모리에서 어떻게 다뤄지는지**입니다.

### **레퍼런스 메모리 구조**
```cpp
int a = 10;
int &ref = a;  // a의 또 다른 이름
```
- `ref`는 `a`와 같은 메모리 주소를 공유하며, 별도의 주소를 가지지 않습니다.
- `ref` 자체는 주소 값을 저장하지 않고, `a`와 동일한 변수처럼 동작합니다.

| 변수명 | 메모리 주소 | 값 |
|------|------|------|
| `a` | `0x100` | `10` |
| `ref` | `0x100` | `10` (같은 주소 공유) |

---

### **포인터 메모리 구조**
```cpp
int a = 10;
int *ptr = &a;  // a의 주소를 저장하는 포인터
```
- `ptr`은 `a`의 주소를 저장하는 변수이며, 자체적으로 주소를 가집니다.

| 변수명 | 메모리 주소 | 값 |
|------|------|------|
| `a` | `0x100` | `10` |
| `ptr` | `0x200` | `0x100` (a의 주소) |

- `ptr`이 `a`를 가리키지만, `ptr` 자체는 `0x200` 주소에 저장됩니다.

---

## **3. 재할당 가능 여부**
레퍼런스는 한 번 선언하면 다른 변수를 가리킬 수 **없지만**, 포인터는 다른 주소로 변경이 가능합니다.

### **레퍼런스 재할당 불가**
```cpp
int a = 10;
int b = 20;
int &ref = a;

ref = b;  // a = 20으로 변경됨 (ref가 b를 가리키는 것이 아님!)
std::cout << "a: " << a << std::endl; // 출력: 20
```
💡 **ref를 `b`로 재할당한 것이 아니라, `a`의 값이 바뀐 것!**

---

### **포인터 재할당 가능**
```cpp
int a = 10;
int b = 20;
int *ptr = &a;  // ptr이 a를 가리킴

ptr = &b;  // ptr이 이제 b를 가리킴
std::cout << "ptr이 가리키는 값: " << *ptr << std::endl; // 출력: 20
```
💡 **포인터는 가리키는 변수를 바꿀 수 있음!**

---

## **4. NULL 가능 여부**
레퍼런스는 반드시 초기화해야 하며, NULL을 가질 수 없습니다.

### **레퍼런스는 NULL이 불가능**
```cpp
int &ref;  // ❌ 컴파일 오류: 레퍼런스는 NULL이 될 수 없음!
```
**하지만 포인터는 NULL을 가질 수 있어 안전성을 체크할 수 있습니다.**

### **포인터는 NULL 가능**
```cpp
int *ptr = nullptr;  // 안전한 초기화
if (ptr) {
    std::cout << "유효한 포인터" << std::endl;
} else {
    std::cout << "NULL 포인터" << std::endl;  // 출력됨
}
```

---

## **5. 동적 메모리 할당 차이**
**레퍼런스는 동적 할당이 불가능하지만, 포인터는 가능**합니다.

### **포인터를 이용한 동적 할당**
```cpp
int *ptr = new int(10);  // 동적으로 메모리 할당
std::cout << *ptr << std::endl;  // 출력: 10
delete ptr;  // 메모리 해제
```
💡 **동적 할당된 메모리는 반드시 `delete`를 사용해 해제해야 함!**

### **레퍼런스를 이용한 동적 할당 (불가능)**
```cpp
int &ref = *(new int(10));  // ❌ 위험한 코드 (delete할 방법이 없음!)
```
💡 **레퍼런스는 동적 할당을 지원하지 않으므로, 메모리 해제를 할 수 없음!**

---

## **6. ROS2에서의 사용 예시**
### **레퍼런스를 활용한 콜백 함수**
ROS2에서 메시지 콜백을 받을 때, **레퍼런스를 사용하면 불필요한 복사를 방지**할 수 있습니다.
```cpp
void callback(const std_msgs::msg::String::SharedPtr &msg) {  
    RCLCPP_INFO(this->get_logger(), "Received: '%s'", msg->data.c_str());
}
```
💡 `msg`를 레퍼런스로 받으면 **복사 없이 직접 메시지에 접근**할 수 있어 성능이 향상됩니다.

---

### **포인터를 활용한 노드 관리**
ROS2에서는 `std::shared_ptr`을 이용해 노드 객체를 관리합니다.
```cpp
rclcpp::Node::SharedPtr node = std::make_shared<rclcpp::Node>("my_node");
```
💡 스마트 포인터를 사용하면 자동으로 메모리를 관리할 수 있습니다.

---

## **7. 레퍼런스 vs 포인터 선택 기준**
| 상황 | 레퍼런스 사용 | 포인터 사용 |
|------|------------|------------|
| 변수를 다른 이름으로 사용 | ✅ | ❌ |
| NULL 값이 필요한 경우 | ❌ | ✅ |
| 변수의 재할당이 필요한 경우 | ❌ | ✅ |
| 동적 메모리 할당 | ❌ | ✅ |
| 안전한 코드 작성 | ✅ | ❌ (Raw Pointer는 메모리 누수 위험) |
| ROS2에서 스마트 포인터 사용 | ❌ | ✅ (`std::shared_ptr`) |

---

## **📌 정리**
- **레퍼런스(`&`)**  
  - 변수의 별칭(Alias) 역할을 하며, 초기화 이후 변경 불가.  
  - NULL이 될 수 없고, 동적 할당 불가능.  
  - **ROS2에서 메시지 콜백 최적화 시 자주 사용됨.**

- **포인터(`*`)**  
  - 변수의 주소를 저장하며, 다른 변수를 가리킬 수 있음.  
  - NULL 가능, 동적 할당 가능, `new/delete` 필요.  
  - **ROS2에서 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 적극 활용.**

💡 **ROS2에서는 스마트 포인터(`std::shared_ptr`)를 기본적으로 사용하고, 성능 최적화를 위해 레퍼런스를 활용한다.**

---

이제 레퍼런스와 포인터의 차이가 명확해졌나요? 추가 질문이 있으면 언제든지 물어보세요! 🚀

<br>
<br>
<br>

## **📌 C++에서 `->` 와 `.` 의 차이점**
C++에서는 `.` (dot operator)과 `->` (arrow operator)를 모두 사용할 수 있지만, **사용하는 대상이 다릅니다**.

| 연산자 | 사용 대상 | 예제 |
|------|---------|-------|
| `.` (dot operator) | **객체(Object)** | `object.function()` |
| `->` (arrow operator) | **포인터(Pointer)** | `ptr->function()` |

💡 **즉, `.` 는 일반 객체에서 멤버 접근할 때 사용하고, `->` 는 포인터가 가리키는 객체의 멤버에 접근할 때 사용합니다.**

---

## **1️⃣ `.` (dot operator) - 객체를 직접 사용할 때**
💡 **객체(Instance)를 직접 사용할 경우 `.`을 사용하여 멤버에 접근**  
```cpp
#include <iostream>

class Car {
public:
    void drive() {
        std::cout << "자동차가 달립니다!" << std::endl;
    }
};

int main() {
    Car myCar;  // 객체 생성
    myCar.drive();  // ✅ 객체가 직접 멤버 함수 호출 (dot operator 사용)
    return 0;
}
```
✅ **여기서 `myCar`는 `Car` 객체이며, `myCar.drive();`를 통해 `drive()` 멤버 함수에 접근**  

---

## **2️⃣ `->` (arrow operator) - 포인터를 사용할 때**
💡 **포인터가 객체를 가리키는 경우 `->`를 사용하여 멤버에 접근**  
```cpp
#include <iostream>

class Car {
public:
    void drive() {
        std::cout << "자동차가 달립니다!" << std::endl;
    }
};

int main() {
    Car* carPtr = new Car();  // 객체를 동적 할당하여 포인터로 관리
    carPtr->drive();  // ✅ 포인터를 통해 멤버 함수 호출 (arrow operator 사용)

    delete carPtr;  // 동적 할당된 메모리 해제
    return 0;
}
```
✅ **여기서 `carPtr`은 `Car` 객체를 가리키는 포인터이며, `carPtr->drive();`를 통해 멤버 함수 호출**

---

## **3️⃣ `.` 와 `->` 를 함께 쓰는 경우**
💡 **객체가 포인터로 접근 가능한 경우, `.`을 사용하여 포인터 해제 후 접근할 수도 있음.**
```cpp
#include <iostream>

class Car {
public:
    void drive() {
        std::cout << "자동차가 달립니다!" << std::endl;
    }
};

int main() {
    Car myCar;   // 일반 객체
    Car* carPtr = &myCar;  // 포인터가 객체를 가리킴

    myCar.drive();    // ✅ 객체 직접 접근 (dot operator)
    carPtr->drive();  // ✅ 포인터를 통해 접근 (arrow operator)
    (*carPtr).drive();  // ✅ 포인터를 역참조 후 dot operator 사용

    return 0;
}
```
✅ **`(*carPtr).drive();` → 포인터를 역참조한 후 `.`을 사용하여 멤버 함수 호출 가능**  
✅ **하지만 `carPtr->drive();`가 더 직관적이고 일반적으로 사용됨.**

---

## **4️⃣ 클래스 멤버 접근에서 `.` vs `->`**
💡 **클래스 멤버 변수에 접근하는 경우에도 동일한 원칙이 적용됨.**
```cpp
#include <iostream>

class Person {
public:
    std::string name;
    int age;
};

int main() {
    Person person1;
    person1.name = "Alice";  // ✅ 일반 객체는 dot 사용
    person1.age = 25;

    Person* personPtr = &person1;
    personPtr->name = "Bob";  // ✅ 포인터는 arrow 사용
    personPtr->age = 30;

    std::cout << "이름: " << person1.name << ", 나이: " << person1.age << std::endl;
    return 0;
}
```
✅ **일반 객체에서는 `.` 사용, 포인터에서는 `->` 사용**

---

## **5️⃣ `std::shared_ptr` 와 `std::unique_ptr` 사용 시**
💡 **C++ 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`) 를 사용할 때도 `->`를 사용**  
```cpp
#include <iostream>
#include <memory>  // 스마트 포인터 사용을 위한 헤더

class Car {
public:
    void drive() {
        std::cout << "스마트 포인터를 사용한 자동차가 달립니다!" << std::endl;
    }
};

int main() {
    std::shared_ptr<Car> carPtr = std::make_shared<Car>();
    carPtr->drive();  // ✅ 스마트 포인터에서도 arrow operator 사용

    return 0;
}
```
✅ **스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)는 포인터처럼 동작하므로 `->` 사용**

---

## **6️⃣ `tf2_ros::Buffer` 와 `lookupTransform()` 에서 `->` 사용**
💡 **ROS2에서 `tf2_ros::Buffer` 객체를 포인터로 선언했기 때문에 `->` 사용**

```cpp
std::shared_ptr<tf2_ros::Buffer> tf_buffer_;
tf_buffer_ = std::make_shared<tf2_ros::Buffer>(this->get_clock());

// ✅ 포인터이므로 `->` 사용
transform = tf_buffer_->lookupTransform("base_link", "laser", tf2::TimePointZero);
```
✅ **`tf_buffer_`는 `std::shared_ptr<tf2_ros::Buffer>` 타입이므로 `->` 연산자를 사용해야 함**  
✅ **만약 `tf2_ros::Buffer` 객체를 직접 선언했다면 `.` 연산자를 사용할 수 있음**
```cpp
tf2_ros::Buffer tf_buffer(this->get_clock());
transform = tf_buffer.lookupTransform("base_link", "laser", tf2::TimePointZero);
```

---

## **📌 최종 정리**
| 사용 대상 | 연산자 | 예제 |
|---------|------|----------------------|
| **일반 객체** | `.` | `object.function()` |
| **포인터가 가리키는 객체** | `->` | `ptr->function()` |
| **포인터를 역참조한 후 접근** | `.` | `(*ptr).function()` |
| **스마트 포인터 사용 (`std::shared_ptr`)** | `->` | `shared_ptr_obj->function()` |
| **ROS2 TF2 사용 (`tf2_ros::Buffer`)** | `->` | `tf_buffer_->lookupTransform(...)` |

✅ **객체를 직접 사용할 때는 `.` 를 사용하고, 포인터를 통해 접근할 때는 `->` 를 사용하면 된다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>


# **3. 객체지향 프로그래밍 (OOP)과 ROS2 적용**

객체지향 프로그래밍(OOP)은 **코드를 구조화하고 재사용성을 높이는 중요한 개념**입니다.  
ROS2에서는 **노드, 메시지 처리, 액션 서버, 서비스 서버** 등의 구현에 OOP를 활용합니다.

---

## **1. 클래스와 객체**
C++에서 **클래스(Class)** 는 객체(Object)를 생성하는 틀(Template)입니다.

### **클래스와 객체 기본 예제**
```cpp
#include <iostream>

// 클래스 정의
class Robot {
public:
    std::string name;

    void say_hello() {
        std::cout << "Hello, I'm " << name << "!" << std::endl;
    }
};

int main() {
    Robot r1;         // 객체 생성
    r1.name = "ROSBot";
    r1.say_hello();   // 메서드 호출

    return 0;
}
```
💡 `Robot` 클래스는 `name` 속성과 `say_hello()` 메서드를 가지고 있으며, `r1` 객체를 생성하여 사용합니다.

---

## **2. 생성자(Constructor)와 소멸자(Destructor)**
### **생성자(Constructor)**
- **객체가 생성될 때 자동으로 호출**되는 함수.
- 객체의 초기화를 담당.
- 함수명은 **클래스명과 동일**하며 반환값이 없음.

### **소멸자(Destructor)**
- **객체가 소멸될 때 자동으로 호출**되는 함수.
- 메모리를 정리하거나, 종료 시 필요한 동작 수행.
- **클래스명 앞에 `~` 기호**를 붙여 정의.

🔹 **생성자와 소멸자 예제**
```cpp
#include <iostream>

class Robot {
public:
    std::string name;

    // 생성자
    Robot(std::string robot_name) {
        name = robot_name;
        std::cout << name << " 로봇이 생성되었습니다!" << std::endl;
    }

    // 소멸자
    ~Robot() {
        std::cout << name << " 로봇이 소멸되었습니다!" << std::endl;
    }

    void say_hello() {
        std::cout << "Hello, I'm " << name << "!" << std::endl;
    }
};

int main() {
    Robot r1("ROSBot");  // 생성자 자동 호출
    r1.say_hello();      

    return 0;  // 프로그램 종료 시 소멸자 자동 호출
}
```
💡 `Robot("ROSBot")`을 생성할 때 생성자가 실행되며, 프로그램이 종료되면 소멸자가 실행됩니다.

---

## **3. 접근 지정자 (public, private, protected)**
- **`public`**: 외부에서 접근 가능.
- **`private`**: 클래스 내부에서만 접근 가능.
- **`protected`**: 상속받은 클래스에서만 접근 가능.

🔹 **접근 지정자 예제**
```cpp
#include <iostream>

class Robot {
private:
    int battery_level;  // 외부에서 접근 불가

public:
    std::string name;

    Robot(std::string robot_name) : name(robot_name), battery_level(100) {}

    void show_status() {
        std::cout << name << " 배터리: " << battery_level << "%" << std::endl;
    }
};

int main() {
    Robot r1("ROSBot");
    r1.name = "NewBot";   // ✅ public 변수 접근 가능
    // r1.battery_level = 50;  // ❌ private 변수 접근 불가 (컴파일 오류)
    r1.show_status();

    return 0;
}
```
💡 `battery_level`은 `private`이므로 외부에서 직접 수정할 수 없으며, `show_status()` 같은 public 메서드를 통해 접근해야 합니다.

---

## **4. 상속과 다형성**
### **상속 (Inheritance)**
- 기존 클래스를 확장하여 새로운 클래스를 생성하는 기능.
- **기본 클래스(부모) → 파생 클래스(자식)** 관계.

🔹 **상속 예제**
```cpp
#include <iostream>

// 부모 클래스
class Robot {
public:
    std::string name;
    Robot(std::string robot_name) : name(robot_name) {}

    void show_status() {
        std::cout << name << " is operational!" << std::endl;
    }
};

// 자식 클래스
class FlyingRobot : public Robot {
public:
    FlyingRobot(std::string robot_name) : Robot(robot_name) {}

    void fly() {
        std::cout << name << " is flying!" << std::endl;
    }
};

int main() {
    FlyingRobot r2("FlyBot");
    r2.show_status();  // 부모 클래스 함수 사용 가능
    r2.fly();          // 자식 클래스 함수 실행

    return 0;
}
```
💡 `FlyingRobot` 클래스는 `Robot` 클래스를 상속받아 기존 기능을 확장했습니다.

---

### **다형성(Polymorphism)과 `virtual` 키워드**
- 부모 클래스의 함수를 **자식 클래스에서 재정의(Override)** 하여 다르게 동작하도록 만듦.

🔹 **다형성 예제**
```cpp
#include <iostream>

class Robot {
public:
    std::string name;

    Robot(std::string robot_name) : name(robot_name) {}

    virtual void action() {  // 가상 함수
        std::cout << name << " is moving." << std::endl;
    }
};

class FlyingRobot : public Robot {
public:
    FlyingRobot(std::string robot_name) : Robot(robot_name) {}

    void action() override {  // 함수 재정의
        std::cout << name << " is flying!" << std::endl;
    }
};

int main() {
    Robot *robot = new FlyingRobot("FlyBot");
    robot->action();  // "FlyBot is flying!" 출력

    delete robot;
    return 0;
}
```
💡 `virtual`을 사용하면 부모 클래스의 함수를 **자식 클래스에서 오버라이딩(Override)** 할 수 있습니다.

---

## **5. 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)**
### **ROS2에서 스마트 포인터를 사용하는 이유**
- **메모리 누수를 방지**하고 객체를 자동으로 관리.
- **RAII(Resource Acquisition Is Initialization) 원칙**을 적용하여 객체를 안전하게 관리.

🔹 **`std::shared_ptr` (참조 카운트 기반)**
```cpp
#include <iostream>
#include <memory>

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 생성됨!" << std::endl;
    }
    ~Robot() {
        std::cout << name << " 소멸됨!" << std::endl;
    }
    void say_hello() {
        std::cout << "Hello, I'm " << name << "!" << std::endl;
    }

private:
    std::string name;
};

int main() {
    std::shared_ptr<Robot> r1 = std::make_shared<Robot>("ROSBot");
    r1->say_hello();

    std::shared_ptr<Robot> r2 = r1;  // 참조 카운트 증가
    r2->say_hello();

    return 0;  // 참조 카운트가 0이 되면 객체 자동 삭제
}
```
💡 `std::shared_ptr`를 사용하면 `r1`과 `r2`가 같은 객체를 공유하며, 마지막 참조가 사라질 때 객체가 소멸됩니다.

---

🔹 **`std::unique_ptr` (단독 소유)**
```cpp
std::unique_ptr<Robot> r = std::make_unique<Robot>("SoloBot");
```
💡 `std::unique_ptr`은 하나의 포인터만 객체를 소유하며, `std::move()`를 사용해 소유권을 이전해야 합니다.

---

## **📌 정리**
- **클래스와 객체**: ROS2에서 노드 및 기능을 객체로 분리하여 구현.
- **생성자 & 소멸자**: 노드 생성 및 종료 시 필요한 초기화/정리 작업에 활용.
- **접근 지정자**: `private`을 사용해 중요한 데이터를 보호.
- **상속 & 다형성**: 로봇의 다양한 기능을 확장하는 데 활용.
- **스마트 포인터**: ROS2에서 노드와 메시지를 안전하게 관리.

이해가 잘 되셨나요? 추가 질문이 있으면 알려주세요! 🚀

<br>
<br>
<br>

## **접근 지정자 (`public`, `private`, `protected`)와 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`) 자세한 설명과 예제**

---

# **1. 접근 지정자 (`public`, `private`, `protected`)**

C++에서 **접근 지정자**는 클래스 내부의 멤버 변수 및 함수를 **어디서 접근할 수 있는지**를 결정합니다.

| 접근 지정자 | 설명 | 클래스 내부 | 상속받은 클래스 | 외부(객체 사용) |
|-----------|--------------------------------|------------|--------------|------------|
| `public` | 모든 곳에서 접근 가능 | ✅ | ✅ | ✅ |
| `private` | 클래스 내부에서만 접근 가능 | ✅ | ❌ | ❌ |
| `protected` | 클래스 내부 + 상속받은 클래스에서 접근 가능 | ✅ | ✅ | ❌ |

---

## **1.1 `public`, `private`, `protected` 기본 예제**
```cpp
#include <iostream>

class Robot {
private:
    int battery_level = 100; // 외부 접근 불가

protected:
    std::string model = "Standard"; // 자식 클래스에서는 접근 가능

public:
    std::string name;

    Robot(std::string robot_name) : name(robot_name) {}

    void show_status() {
        std::cout << "Robot: " << name << ", Battery: " << battery_level << "%, Model: " << model << std::endl;
    }
};

class FlyingRobot : public Robot {
public:
    FlyingRobot(std::string robot_name) : Robot(robot_name) {}

    void show_model() {
        std::cout << "Model: " << model << std::endl;  // protected 멤버 접근 가능 (상속받은 클래스)
    }
};

int main() {
    Robot r1("ROSBot");
    r1.name = "NewBot";   // ✅ public 멤버 접근 가능
    // r1.battery_level = 50;  // ❌ private 멤버 접근 불가 (컴파일 오류)
    r1.show_status();

    FlyingRobot r2("FlyBot");
    r2.show_model();  // ✅ protected 멤버는 상속받은 클래스에서 접근 가능

    return 0;
}
```
### **🔹 주요 개념**
- `battery_level`(private) → **Robot 내부에서만 사용 가능**
- `model`(protected) → **FlyingRobot 클래스에서도 사용 가능**
- `name`(public) → **객체를 통해 어디서든 접근 가능**

---

## **1.2 Getter와 Setter를 활용한 `private` 멤버 접근**
`private` 멤버 변수를 직접 수정할 수 없지만, **Getter와 Setter 함수**를 사용하면 가능하게 만들 수 있습니다.

```cpp
#include <iostream>

class Robot {
private:
    int battery_level;

public:
    Robot() : battery_level(100) {}

    int getBatteryLevel() { // Getter
        return battery_level;
    }

    void setBatteryLevel(int level) { // Setter
        if (level >= 0 && level <= 100) {
            battery_level = level;
        } else {
            std::cout << "Invalid battery level!" << std::endl;
        }
    }
};

int main() {
    Robot r;
    r.setBatteryLevel(80); // ✅ Setter로 값 변경
    std::cout << "Battery: " << r.getBatteryLevel() << "%" << std::endl; // ✅ Getter로 값 읽기

    return 0;
}
```
💡 **Setter를 통해 값의 유효성을 검사할 수 있음** (0~100 사이 값만 허용)

---

## **2. 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)**
C++에서 스마트 포인터를 사용하면 **메모리 해제를 자동화**할 수 있습니다.

---

## **2.1 `std::shared_ptr` - 참조 카운트를 이용한 메모리 공유**
- 여러 개의 `std::shared_ptr`가 같은 객체를 공유할 수 있음.
- 마지막 `shared_ptr`이 소멸될 때 메모리가 자동 해제됨.

### **🔹 `std::shared_ptr` 기본 예제**
```cpp
#include <iostream>
#include <memory>

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 로봇 생성!" << std::endl;
    }
    ~Robot() {
        std::cout << name << " 로봇 소멸!" << std::endl;
    }
    void sayHello() {
        std::cout << "Hello, I'm " << name << "!" << std::endl;
    }

private:
    std::string name;
};

int main() {
    std::shared_ptr<Robot> r1 = std::make_shared<Robot>("ROSBot");
    {
        std::shared_ptr<Robot> r2 = r1;  // r1과 r2가 같은 객체를 공유
        r2->sayHello();
    } // r2가 범위를 벗어나지만, r1이 남아있으므로 객체는 삭제되지 않음

    std::cout << "r1이 마지막 소유자입니다." << std::endl;
    return 0; // r1이 사라지면서 객체 자동 소멸
}
```
### **🔹 실행 결과**
```
ROSBot 로봇 생성!
Hello, I'm ROSBot!
r1이 마지막 소유자입니다.
ROSBot 로봇 소멸!
```
💡 `std::shared_ptr`는 참조 카운트를 관리하여 **누군가 객체를 참조하는 동안에는 삭제되지 않음**.

---

## **2.2 `std::unique_ptr` - 단독 소유 스마트 포인터**
- 한 개의 `std::unique_ptr`만 객체를 소유할 수 있음.
- `std::move()`를 사용하여 소유권을 이전 가능.

### **🔹 `std::unique_ptr` 기본 예제**
```cpp
#include <iostream>
#include <memory>

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 생성됨!" << std::endl;
    }
    ~Robot() {
        std::cout << name << " 소멸됨!" << std::endl;
    }
    void sayHello() {
        std::cout << "Hello, I'm " << name << "!" << std::endl;
    }

private:
    std::string name;
};

int main() {
    std::unique_ptr<Robot> r1 = std::make_unique<Robot>("UniqueBot");

    // std::unique_ptr는 복사할 수 없음
    // std::unique_ptr<Robot> r2 = r1;  // ❌ 컴파일 오류!

    // std::move()를 사용하면 소유권을 이전할 수 있음
    std::unique_ptr<Robot> r2 = std::move(r1);
    r2->sayHello();  // ✅ r2가 소유권을 가지므로 사용 가능

    return 0; // r2가 범위를 벗어나면서 자동 소멸
}
```
💡 **`std::unique_ptr`는 한 개의 포인터만 객체를 소유할 수 있으며, `std::move()`를 통해 소유권을 넘겨야 함**.

---

## **2.3 `std::weak_ptr` - 순환 참조 방지**
`std::weak_ptr`은 **객체를 참조할 수 있지만 소유권을 갖지 않음**.  
즉, `shared_ptr`가 메모리를 해제할 때 `weak_ptr`는 그 메모리를 해제하지 않음.

### **🔹 `std::weak_ptr`을 활용한 순환 참조 방지**
```cpp
#include <iostream>
#include <memory>

class Robot {
public:
    std::shared_ptr<Robot> friend_robot;  // 순환 참조 발생 가능

    Robot() {
        std::cout << "로봇 생성됨!" << std::endl;
    }

    ~Robot() {
        std::cout << "로봇 소멸됨!" << std::endl;
    }
};

int main() {
    std::shared_ptr<Robot> r1 = std::make_shared<Robot>();
    std::shared_ptr<Robot> r2 = std::make_shared<Robot>();

    r1->friend_robot = r2;  // r1이 r2를 참조
    r2->friend_robot = r1;  // r2가 r1을 참조 (순환 참조 발생!)

    return 0;  // ❌ 메모리 누수 발생 (소멸자가 호출되지 않음!)
}
```
💡 **해결 방법: `std::weak_ptr` 사용**
```cpp
std::weak_ptr<Robot> friend_robot;  // 소유권 없이 참조만 함
```
이렇게 하면 **순환 참조 문제를 해결**할 수 있습니다.

---

## **📌 정리**
- **`public`, `private`, `protected`**: 데이터 캡슐화를 위해 사용.
- **`std::shared_ptr`**: 여러 곳에서 공유 가능, 자동 해제.
- **`std::unique_ptr`**: 단독 소유, `std::move()` 필요.
- **`std::weak_ptr`**: 순환 참조 방지.

이제 스마트 포인터와 접근 지정자의 차이점이 명확해졌나요? 추가 질문이 있다면 알려주세요! 🚀

<br>
<br>
<br>
<br>

# **4. C++ STL과 ROS2에서의 활용**

C++의 **STL(Standard Template Library)** 은 **데이터 구조와 알고리즘을 제공하는 표준 라이브러리**입니다.  
ROS2에서도 STL의 다양한 컨테이너(`std::vector`, `std::list`, `std::map`, `std::set`)와 문자열 처리 기능(`std::string`, `std::stringstream`)을 활용하여 **메시지 데이터 처리, 센서 데이터 저장, 설정값 관리** 등을 수행할 수 있습니다.

---

# **1. `std::vector` - ROS2 메시지 데이터 저장 활용**
### **📌 `std::vector`란?**
- **동적 배열**을 제공하며, 크기가 자동으로 조절됨.
- **빠른 랜덤 접근 가능** (`O(1)`)
- **push_back()**, **pop_back()** 등으로 데이터 추가/제거 가능.

---

## **1.1 `std::vector` 기본 예제**
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {10, 20, 30, 40};

    // 요소 추가
    numbers.push_back(50);

    // 요소 출력
    for (int num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
**🔹 출력 결과:**  
```
10 20 30 40 50
```

---

## **1.2 `std::vector`를 ROS2에서 활용**
ROS2에서는 **메시지 데이터(센서 값, 경로 데이터 등)를 저장하는 용도**로 `std::vector`를 활용할 수 있습니다.

🔹 **예제: `std::vector`를 활용한 ROS2 퍼블리셔**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/int32_multi_array.hpp"

class VectorPublisher : public rclcpp::Node {
public:
    VectorPublisher() : Node("vector_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::Int32MultiArray>("vector_topic", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1), std::bind(&VectorPublisher::publishData, this));
    }

private:
    void publishData() {
        std_msgs::msg::Int32MultiArray msg;
        msg.data = {10, 20, 30, 40, 50};  // std::vector를 메시지에 사용
        publisher_->publish(msg);
        RCLCPP_INFO(this->get_logger(), "Published vector data!");
    }

    rclcpp::Publisher<std_msgs::msg::Int32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<VectorPublisher>());
    rclcpp::shutdown();
    return 0;
}
```
**🔹 실행하면 `/vector_topic` 에 `[10, 20, 30, 40, 50]` 데이터가 전송됨!**

---

# **2. `std::list`, `std::map`, `std::set` 활용**

## **2.1 `std::list` - 양방향 연결 리스트**
### **📌 `std::list` 특징**
- **노드 기반의 연결 리스트** (메모리 연속성이 없음).
- **중간 삽입/삭제가 빠름 (`O(1)`)** → `push_front()`, `push_back()`
- **랜덤 접근이 느림 (`O(n)`)** → `std::vector`보다 느림.

🔹 **예제: `std::list` 사용**
```cpp
#include <iostream>
#include <list>

int main() {
    std::list<int> numbers = {10, 20, 30};

    numbers.push_front(5);  // 앞에 추가
    numbers.push_back(40);  // 뒤에 추가

    for (int num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
**🔹 출력 결과:**  
```
5 10 20 30 40
```

---

## **2.2 `std::map` - 키-값 쌍 저장**
### **📌 `std::map` 특징**
- **자동 정렬된 키-값 저장소** (`std::map<int, std::string>` 등).
- **중복 키 불가능**.
- **빠른 탐색 (`O(log n)`)**.

🔹 **예제: `std::map` 사용**
```cpp
#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> robot_speeds;

    robot_speeds["TurtleBot"] = 1;
    robot_speeds["ROSBot"] = 3;
    robot_speeds["RoboMaster"] = 5;

    for (const auto &pair : robot_speeds) {
        std::cout << pair.first << ": " << pair.second << " m/s" << std::endl;
    }

    return 0;
}
```
**🔹 출력 결과:**  
```
RoboMaster: 5 m/s
ROSBot: 3 m/s
TurtleBot: 1 m/s
```
💡 **키값으로 자동 정렬됨!**

---

## **2.3 `std::set` - 중복 없는 데이터 저장**
### **📌 `std::set` 특징**
- **중복이 없는 정렬된 데이터 저장소**.
- **탐색 속도가 `O(log n)` 로 빠름**.

🔹 **예제: `std::set` 사용**
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> unique_numbers = {5, 10, 10, 20, 30, 30, 40};

    for (int num : unique_numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
**🔹 출력 결과:**  
```
5 10 20 30 40
```
💡 **중복된 값(10, 30)은 자동으로 제거됨!**

---

# **3. 문자열 처리 (`std::string`, `std::stringstream`)**

## **3.1 `std::string` 활용**
- **문자열 데이터 저장** (`std::string`)
- **문자열 길이 확인** (`length()`)
- **문자열 조작** (`substr()`, `append()`, `find()` 등)

🔹 **예제: `std::string` 기본 활용**
```cpp
#include <iostream>
#include <string>

int main() {
    std::string robot_name = "TurtleBot";
    
    std::cout << "로봇 이름: " << robot_name << std::endl;
    std::cout << "문자 개수: " << robot_name.length() << std::endl;

    return 0;
}
```

---

## **3.2 `std::stringstream` - 문자열을 숫자로 변환**
- **숫자 데이터를 문자열로 변환하거나, 문자열을 숫자로 변환할 때 사용**.

🔹 **예제: `std::stringstream` 활용**
```cpp
#include <iostream>
#include <sstream>

int main() {
    std::stringstream ss;
    ss << "10 20 30";

    int a, b, c;
    ss >> a >> b >> c;

    std::cout << "읽은 값: " << a << ", " << b << ", " << c << std::endl;

    return 0;
}
```
**🔹 출력 결과:**  
```
읽은 값: 10, 20, 30
```
💡 **입력된 문자열을 숫자로 변환하여 사용할 수 있음!**

---

# **📌 정리**
| STL 컨테이너 | 활용 예제 |
|-------------|---------|
| `std::vector` | ROS2 메시지 데이터 저장 |
| `std::list` | 노드 간 데이터 처리 |
| `std::map` | 키-값 저장 (로봇 ID - 속도) |
| `std::set` | 중복 없는 데이터 저장 |
| `std::string` | 텍스트 처리 (로봇 이름, 메시지) |
| `std::stringstream` | 문자열 ↔ 숫자 변환 |

이제 STL 컨테이너와 ROS2에서의 활용법이 명확해졌나요?  
추가 질문이 있다면 언제든지 알려주세요! 🚀

<br>
<br>

## **C++의 `for (const auto &pair : container)` 문법 설명**

해당 문법은 **C++11 이후 도입된 범위 기반 for 문 (range-based for loop)** 을 사용하여 컨테이너(예: `std::map`)를 반복(iterate)할 때 사용됩니다.

### **📌 해당 구문의 의미**
```cpp
for (const auto &pair : robot_speeds)
```
이 구문을 분석해 보면:

| 요소 | 의미 |
|------|------|
| `for` | 반복문 시작 |
| `const` | `pair`가 **수정되지 않도록 보호** (읽기 전용) |
| `auto` | `pair`의 타입을 자동으로 추론 (`std::pair<const std::string, int>`) |
| `&` | 참조로 받아 **복사 비용을 줄임** |
| `pair` | `robot_speeds` 컨테이너의 각 요소 (key-value 쌍) |
| `: robot_speeds` | `robot_speeds` 컨테이너를 순회 |

---

## **1️⃣ 기본 예제: `std::map`을 반복문으로 순회**
```cpp
#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> robot_speeds;
    robot_speeds["TurtleBot"] = 1;
    robot_speeds["ROSBot"] = 3;
    robot_speeds["RoboMaster"] = 5;

    // 범위 기반 for문을 사용하여 std::map의 key-value 쌍을 순회
    for (const auto &pair : robot_speeds) {
        std::cout << pair.first << ": " << pair.second << " m/s" << std::endl;
    }

    return 0;
}
```
### **🔹 출력 결과**
```
RoboMaster: 5 m/s
ROSBot: 3 m/s
TurtleBot: 1 m/s
```
> **✔️ `pair.first`** → 키 (로봇 이름)  
> **✔️ `pair.second`** → 값 (속도)

---

## **2️⃣ `const auto &pair`를 사용하는 이유**
### **(1) `auto &pair` vs `const auto &pair` 비교**
| 코드 | 설명 |
|------|------|
| `for (auto pair : robot_speeds)` | **값 복사** → 성능 저하 (객체가 클 경우 비효율적) |
| `for (auto &pair : robot_speeds)` | **참조 전달** → 복사 방지, 수정 가능 |
| `for (const auto &pair : robot_speeds)` | **참조 전달 + 읽기 전용** → 복사 방지 + 안전 |

💡 **`const auto &pair`** 를 사용하면:
1. **불필요한 복사를 방지** (`std::map`의 요소를 복사하지 않음 → 메모리 절약)
2. **읽기 전용으로 안전하게 사용** (데이터가 변경되지 않도록 보장)

---

## **3️⃣ `std::vector`와 함께 사용**
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {10, 20, 30, 40, 50};

    for (const auto &num : numbers) { // 읽기 전용 (안전함)
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
### **🔹 출력 결과**
```
10 20 30 40 50
```
> 💡 `std::vector<int>` 요소를 복사 없이 **참조(&)를 이용하여 읽기 전용(`const`)로 순회**.

---

## **4️⃣ `std::set`과 함께 사용**
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<std::string> robot_models = {"TurtleBot", "ROSBot", "RoboMaster"};

    for (const auto &model : robot_models) {
        std::cout << "Robot: " << model << std::endl;
    }

    return 0;
}
```
> 💡 `std::set<std::string>`도 **자동으로 정렬되며**, 복사 없이 참조로 순회 가능.

---

## **📌 정리**
| 코드 | 의미 | 사용 이유 |
|------|------|---------|
| `for (auto pair : map)` | 복사 | 성능 저하 가능 |
| `for (auto &pair : map)` | 참조 | 복사 방지, 수정 가능 |
| `for (const auto &pair : map)` | **참조 + 읽기 전용** | **복사 방지 + 안전** |

- **`auto &`** → 복사 없이 수정 가능 (⚠️ 원본이 변경됨)
- **`const auto &`** → 복사 없이 **읽기 전용** (✅ 안전)
- 범위 기반 `for` 문은 **STL 컨테이너를 편리하게 순회**하는 방법.

이해가 되셨나요? 추가 질문이 있으면 알려주세요! 🚀

<br>
<br>

## **`std::stringstream`을 활용한 문자열 스트림 처리 문법 설명**

`std::stringstream`은 **C++에서 문자열을 숫자로 변환하거나, 숫자를 문자열로 변환할 때 사용**하는 표준 라이브러리입니다.

---

## **📌 `ss << "10 20 30";` 문법 설명**
```cpp
std::stringstream ss;
ss << "10 20 30";
```
- `std::stringstream` 객체 `ss`를 생성.
- `"10 20 30"` 문자열을 스트림에 입력.
- 내부적으로 `"10 20 30"`이 `ss`에 저장됨.

### **📌 `ss >> a >> b >> c;` 문법 설명**
```cpp
ss >> a >> b >> c;
```
- `ss`에서 공백(스페이스) 단위로 데이터를 읽어 변수 `a`, `b`, `c`에 저장.
- 스트림이 자동으로 **공백을 기준으로 숫자를 분리**해서 읽음.

---

## **🔹 전체 예제**
```cpp
#include <iostream>
#include <sstream>

int main() {
    std::stringstream ss;
    ss << "10 20 30"; // 문자열 데이터를 스트림에 저장

    int a, b, c;
    ss >> a >> b >> c; // 문자열에서 정수로 변환하여 저장

    std::cout << "a: " << a << ", b: " << b << ", c: " << c << std::endl;
    return 0;
}
```
### **🔹 실행 결과**
```
a: 10, b: 20, c: 30
```
💡 **공백(`" "`)을 기준으로 문자열을 분리하여 정수로 변환!**

---

## **1️⃣ `std::stringstream`을 활용한 숫자 → 문자열 변환**
```cpp
#include <iostream>
#include <sstream>

int main() {
    int x = 42, y = 7;
    std::stringstream ss;

    ss << "The answer is " << x + y;

    std::string result = ss.str(); // 스트림을 문자열로 변환
    std::cout << result << std::endl;

    return 0;
}
```
### **🔹 실행 결과**
```
The answer is 49
```
💡 `<<` 연산자를 사용하여 여러 값을 하나의 문자열로 변환할 수 있음.

---

## **2️⃣ `std::stringstream`을 활용한 문자열 → 숫자 변환**
```cpp
#include <iostream>
#include <sstream>

int main() {
    std::string input = "123";
    int number;

    std::stringstream ss(input); // 문자열을 스트림으로 변환
    ss >> number; // 정수로 변환

    std::cout << "숫자로 변환된 값: " << number + 1 << std::endl;
    return 0;
}
```
### **🔹 실행 결과**
```
숫자로 변환된 값: 124
```
💡 **문자열 `"123"`을 정수 `123`으로 변환한 후, `+1`을 수행!**

---

## **3️⃣ `std::stringstream`을 활용한 문자열 분리 (공백 기준)**
```cpp
#include <iostream>
#include <sstream>

int main() {
    std::string input = "ros2 turtlebot slam";
    std::stringstream ss(input);

    std::string word;
    while (ss >> word) { // 공백 단위로 분리
        std::cout << word << std::endl;
    }

    return 0;
}
```
### **🔹 실행 결과**
```
ros2
turtlebot
slam
```
💡 **공백을 기준으로 문자열을 분리하여 출력!**

---

## **📌 정리**
| 기능 | 코드 | 설명 |
|------|------|------|
| **숫자 → 문자열 변환** | `ss << 42;` | `42`를 문자열로 변환 |
| **문자열 → 숫자 변환** | `ss >> number;` | `"123"` → `123`으로 변환 |
| **문자열 분리** | `ss >> word;` | 공백 기준으로 단어 분리 |

✅ `std::stringstream`을 활용하면 **숫자 ↔ 문자열 변환, 공백 기준 데이터 분리** 등을 쉽게 할 수 있음! 🚀

이해되셨나요? 추가 질문이 있으면 알려주세요! 😊

<br>
<br>

C++의 **STL 컨테이너**와 **Python의 내장 자료구조**는 역할과 사용 방식이 유사한 부분이 많습니다.  
Python에서 각각의 STL 컨테이너와 비슷한 개념을 정리해 보겠습니다.

---

## **📌 STL 컨테이너 vs Python 자료구조 비교**

| **C++ STL 컨테이너** | **Python 대응 자료구조** | **설명** |
|-----------------|----------------|------------------------------------------|
| `std::vector<T>` | `list` | 크기 조정이 가능한 동적 배열 |
| `std::list<T>` | `collections.deque` | 양방향 연결 리스트 |
| `std::map<K, V>` | `dict` | 키-값 (key-value) 저장 |
| `std::set<T>` | `set` | 중복 없는 정렬된 집합 |
| `std::string` | `str` | 문자열 처리 |
| `std::stringstream` | `io.StringIO` | 문자열 스트림 |

---

# **1️⃣ `std::vector` ↔ `list` (동적 배열)**
`std::vector`는 **Python의 `list`와 거의 동일한 기능**을 합니다.

### **C++ `std::vector` 예제**
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> v = {1, 2, 3};

    v.push_back(4);  // 요소 추가

    for (int num : v) {
        std::cout << num << " ";
    }

    return 0;
}
```
**🔹 출력 결과**  
```
1 2 3 4
```

### **Python `list` 예제**
```python
v = [1, 2, 3]
v.append(4)  # 요소 추가

print(v)  # [1, 2, 3, 4]
```
**✅ `std::vector`와 `list`는 거의 동일한 동작을 함!**

---

# **2️⃣ `std::list` ↔ `collections.deque` (연결 리스트)**
`std::list`는 **양방향 연결 리스트**이므로, Python의 `collections.deque`와 비슷합니다.  
(`list`도 사용 가능하지만 `deque`가 더 적절함)

### **C++ `std::list` 예제**
```cpp
#include <iostream>
#include <list>

int main() {
    std::list<int> lst = {1, 2, 3};
    lst.push_front(0);  // 앞에 추가
    lst.push_back(4);   // 뒤에 추가

    for (int num : lst) {
        std::cout << num << " ";
    }

    return 0;
}
```
**🔹 출력 결과**  
```
0 1 2 3 4
```

### **Python `deque` 예제**
```python
from collections import deque

lst = deque([1, 2, 3])
lst.appendleft(0)  # 앞에 추가
lst.append(4)      # 뒤에 추가

print(list(lst))  # [0, 1, 2, 3, 4]
```
**✅ `std::list`와 `deque`는 앞뒤 삽입/삭제가 빠르다는 점에서 유사함!**

---

# **3️⃣ `std::map` ↔ `dict` (키-값 저장)**
`std::map`은 **Python의 `dict`와 완전히 동일한 개념**입니다.

### **C++ `std::map` 예제**
```cpp
#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> robot_speeds;
    robot_speeds["TurtleBot"] = 1;
    robot_speeds["ROSBot"] = 3;

    for (const auto &pair : robot_speeds) {
        std::cout << pair.first << ": " << pair.second << std::endl;
    }

    return 0;
}
```
**🔹 출력 결과**
```
ROSBot: 3
TurtleBot: 1
```

### **Python `dict` 예제**
```python
robot_speeds = {
    "TurtleBot": 1,
    "ROSBot": 3
}

for key, value in robot_speeds.items():
    print(f"{key}: {value}")
```
**✅ `std::map`과 `dict`는 동일하게 키-값을 저장하는 기능을 가짐!**

---

# **4️⃣ `std::set` ↔ `set` (중복 없는 집합)**
`std::set`과 Python의 `set`은 **둘 다 중복을 허용하지 않는 정렬된 집합**입니다.

### **C++ `std::set` 예제**
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> unique_numbers = {5, 10, 10, 20, 30, 30, 40};

    for (int num : unique_numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```
**🔹 출력 결과**
```
5 10 20 30 40
```
(중복이 자동으로 제거됨!)

### **Python `set` 예제**
```python
unique_numbers = {5, 10, 10, 20, 30, 30, 40}
print(unique_numbers)  # {5, 10, 20, 30, 40}
```
**✅ `std::set`과 `set`은 중복 제거 기능이 같음!**

---

# **5️⃣ `std::string` ↔ `str` (문자열 처리)**
C++의 `std::string`은 **Python의 `str`과 거의 동일**하지만, 조작 방식이 약간 다릅니다.

### **C++ `std::string` 예제**
```cpp
#include <iostream>
#include <string>

int main() {
    std::string name = "TurtleBot";
    std::cout << "로봇 이름: " << name << std::endl;
    std::cout << "문자 개수: " << name.length() << std::endl;

    return 0;
}
```
**🔹 출력 결과**
```
로봇 이름: TurtleBot
문자 개수: 9
```

### **Python `str` 예제**
```python
name = "TurtleBot"
print(f"로봇 이름: {name}")
print(f"문자 개수: {len(name)}")
```
**✅ `std::string`과 `str`은 같은 기능을 제공!**

---

# **6️⃣ `std::stringstream` ↔ `io.StringIO` (문자열 스트림)**
C++의 `std::stringstream`은 **Python의 `io.StringIO`와 비슷**합니다.

### **C++ `std::stringstream` 예제**
```cpp
#include <iostream>
#include <sstream>

int main() {
    std::stringstream ss;
    ss << "10 20 30";

    int a, b, c;
    ss >> a >> b >> c;

    std::cout << "읽은 값: " << a << ", " << b << ", " << c << std::endl;
    return 0;
}
```
**🔹 출력 결과**
```
읽은 값: 10, 20, 30
```

### **Python `io.StringIO` 예제**
```python
import io

ss = io.StringIO("10 20 30")
data = ss.read().split()  # 공백 기준으로 분리
a, b, c = map(int, data)  # 숫자로 변환

print(f"읽은 값: {a}, {b}, {c}")
```
**✅ `std::stringstream`과 `io.StringIO`는 문자열을 다룰 때 유사한 역할을 수행!**

---

## **📌 결론: C++ STL vs Python**
| **C++ STL** | **Python 대응** | **특징** |
|------------|--------------|----------|
| `std::vector` | `list` | 동적 배열 |
| `std::list` | `collections.deque` | 연결 리스트 |
| `std::map` | `dict` | 키-값 저장 |
| `std::set` | `set` | 중복 없는 집합 |
| `std::string` | `str` | 문자열 처리 |
| `std::stringstream` | `io.StringIO` | 문자열 스트림 |

💡 Python에서는 **더 간결한 문법**을 제공하지만, C++의 STL은 **더 강력한 성능과 제어권**을 제공합니다!

이해가 되셨나요? 추가 질문이 있으면 알려주세요! 🚀

<br>
<br>
<br>
<br>

# **5. C++ 멀티스레딩과 병렬 프로그래밍 (ROS2에서의 활용)**

ROS2에서는 멀티스레딩과 비동기 프로그래밍을 적극 활용하여 **다중 노드 실행, 실시간 센서 데이터 처리, 병렬 연산** 등을 수행합니다.  
이를 위해 C++ 표준 라이브러리의 `std::thread`, `std::mutex`, `std::condition_variable`, `std::async`, `std::future` 등을 사용하며,  
ROS2에서는 `rclcpp::executors::MultiThreadedExecutor`를 통해 멀티스레딩 환경을 효과적으로 관리할 수 있습니다.

---

## **1️⃣ C++ 스레드 (`std::thread`)**

### **📌 `std::thread`란?**
- C++11 이후 표준 라이브러리에 포함된 **경량 스레드 기능**.
- 하나의 프로그램에서 여러 개의 작업을 **동시에 실행** 가능.

### **🔹 기본 예제: `std::thread` 사용**
```cpp
#include <iostream>
#include <thread>

void task() {
    std::cout << "스레드에서 실행됨!" << std::endl;
}

int main() {
    std::thread t(task);  // 새로운 스레드 실행
    t.join();  // 메인 스레드가 t를 기다림 (동기화)
    return 0;
}
```
**🔹 실행 결과**
```
스레드에서 실행됨!
```
💡 **`join()`을 사용하지 않으면 메인 스레드가 종료될 때 t도 강제 종료될 수 있음!**

---

## **2️⃣ `std::mutex`를 이용한 동기화 (스레드 간 데이터 충돌 방지)**

### **📌 `std::mutex`란?**
- **여러 스레드가 공유 자원에 동시에 접근할 때 발생하는 문제 (race condition)를 방지**하기 위해 사용.
- **lock/unlock을 통해 하나의 스레드만 자원에 접근 가능**.

### **🔹 예제: `std::mutex`를 이용한 동기화**
```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;  // 뮤텍스 객체 생성

void printMessage(const std::string &msg) {
    std::lock_guard<std::mutex> lock(mtx);  // 자동으로 락/언락 처리
    std::cout << msg << std::endl;
}

int main() {
    std::thread t1(printMessage, "Thread 1 실행");
    std::thread t2(printMessage, "Thread 2 실행");

    t1.join();
    t2.join();

    return 0;
}
```
**🔹 실행 결과**
```
Thread 1 실행
Thread 2 실행
```
(실행 순서는 랜덤하게 변경될 수 있음)

💡 **`std::lock_guard<std::mutex>`을 사용하면 `lock()`과 `unlock()`을 자동으로 처리하여 deadlock을 방지할 수 있음!**

---

## **3️⃣ `std::condition_variable`을 이용한 스레드 간 동기화**
- 특정 조건이 만족될 때까지 스레드를 대기하도록 만들 수 있음.

### **🔹 예제: 생산자-소비자 문제**
```cpp
#include <iostream>
#include <thread>
#include <queue>
#include <mutex>
#include <condition_variable>

std::queue<int> dataQueue;
std::mutex mtx;
std::condition_variable cv;

void producer() {
    for (int i = 1; i <= 5; i++) {
        std::unique_lock<std::mutex> lock(mtx);
        dataQueue.push(i);
        std::cout << "생산: " << i << std::endl;
        cv.notify_one();  // 소비자에게 알림
    }
}

void consumer() {
    for (int i = 1; i <= 5; i++) {
        std::unique_lock<std::mutex> lock(mtx);
        cv.wait(lock, [] { return !dataQueue.empty(); });  // 큐가 비어있으면 대기
        int value = dataQueue.front();
        dataQueue.pop();
        std::cout << "소비: " << value << std::endl;
    }
}

int main() {
    std::thread t1(producer);
    std::thread t2(consumer);

    t1.join();
    t2.join();

    return 0;
}
```
**🔹 실행 결과**
```
생산: 1
소비: 1
생산: 2
소비: 2
...
```
💡 **`cv.notify_one()`을 통해 소비자 스레드를 깨울 수 있음!**

---

## **4️⃣ `std::async`와 `std::future`를 활용한 비동기 프로그래밍**
### **📌 `std::async`란?**
- 비동기적으로 함수를 실행하여 결과를 나중에 받을 수 있음.
- `std::future`을 통해 **결과를 기다릴 수도 있고, 필요할 때만 가져올 수도 있음**.

### **🔹 예제: `std::async`를 활용한 병렬 계산**
```cpp
#include <iostream>
#include <future>

int computeSquare(int x) {
    return x * x;
}

int main() {
    std::future<int> result = std::async(computeSquare, 5);
    std::cout << "결과: " << result.get() << std::endl;  // get()이 결과를 기다림
    return 0;
}
```
**🔹 실행 결과**
```
결과: 25
```
💡 **`std::async`는 내부적으로 스레드를 관리하므로 직접 `std::thread`를 만들 필요 없음!**

---

# **5️⃣ ROS2 Executor와 멀티스레딩 전략**
## **ROS2의 Executor란?**
- ROS2는 노드(Node)를 실행할 때 Executor(실행자)를 사용.
- Executor는 **콜백(Callback) 함수들을 효율적으로 실행하는 역할**.

### **📌 `SingleThreadedExecutor` (단일 스레드)**
```cpp
rclcpp::executors::SingleThreadedExecutor executor;
executor.add_node(my_node);
executor.spin();
```
**🔹 실행 방식**  
- 한 번에 **하나의 콜백만 실행** (멀티스레딩 지원 X)
- 여러 개의 토픽/타이머가 동시에 실행될 때 **병목 현상 발생 가능**

---

## **6️⃣ `rclcpp::executors::MultiThreadedExecutor` 사용법**
### **📌 `MultiThreadedExecutor` (멀티스레드)**
- 여러 개의 스레드를 생성하여 **콜백을 병렬로 실행**.
- **센서 데이터 수집, 복잡한 계산, 다중 퍼블리셔-서브스크라이버 실행에 적합**.

### **🔹 예제: `MultiThreadedExecutor` 사용**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <thread>

class MultiThreadedNode : public rclcpp::Node {
public:
    MultiThreadedNode() : Node("multi_threaded_node") {
        timer1_ = this->create_wall_timer(std::chrono::seconds(1), 
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 1 실행"); });

        timer2_ = this->create_wall_timer(std::chrono::seconds(1), 
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 2 실행"); });
    }

private:
    rclcpp::TimerBase::SharedPtr timer1_;
    rclcpp::TimerBase::SharedPtr timer2_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedNode>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();

    rclcpp::shutdown();
    return 0;
}
```
💡 **멀티스레드 실행 덕분에 `timer1`과 `timer2`가 병렬로 실행됨!**

---

# **📌 정리**
| 개념 | 사용 이유 |
|------|---------|
| `std::thread` | 기본 멀티스레딩 |
| `std::mutex` | 동기화 (데이터 충돌 방지) |
| `std::condition_variable` | 스레드 간 동기화 |
| `std::async`, `std::future` | 비동기 연산 |
| `SingleThreadedExecutor` | 단일 스레드 ROS2 실행 |
| `MultiThreadedExecutor` | ROS2 멀티스레딩 실행 |

이제 ROS2에서 멀티스레딩과 병렬 프로그래밍을 이해할 수 있겠죠? 🚀  
추가 질문이 있으면 언제든지 알려주세요! 😊

<br>
<br>
<br>

## **C++ 멀티스레딩에서 `std::queue`, `std::condition_variable`을 활용한 생산자-소비자 패턴 문법 설명**

해당 코드는 **생산자-소비자 패턴(Producer-Consumer Pattern)** 을 구현하는 데 사용됩니다.  
`std::queue`와 `std::condition_variable`을 활용하여 **생산자는 데이터를 큐에 추가하고, 소비자는 큐에 데이터가 들어올 때까지 기다리는 구조**입니다.

---

# **📌 코드 분석**
```cpp
std::queue<int> dataQueue;
std::mutex mtx;
std::condition_variable cv;
```
- `std::queue<int> dataQueue;` → **생산자가 데이터를 저장하는 큐**
- `std::mutex mtx;` → **큐에 대한 접근을 동기화하기 위한 뮤텍스**
- `std::condition_variable cv;` → **소비자가 데이터를 기다릴 수 있도록 하는 조건 변수**

---

## **1️⃣ `dataQueue.push(i);` - 큐에 데이터 추가 (생산자 역할)**
```cpp
std::unique_lock<std::mutex> lock(mtx);  // 뮤텍스 잠금
dataQueue.push(i);  // 데이터 추가
cv.notify_one();  // 소비자에게 알림
```
### **📌 동작 원리**
1. `std::unique_lock<std::mutex> lock(mtx);`
   - **뮤텍스를 잠금(lock)하여 다른 스레드가 큐를 수정하지 못하도록 함.**
   - `std::lock_guard<std::mutex>`도 가능하지만 `unique_lock`이 더 유연함.
  
2. `dataQueue.push(i);`
   - **큐에 새로운 데이터를 추가**.

3. `cv.notify_one();`
   - **대기 중인 소비자 스레드 중 하나를 깨움**.
   - **큐가 비어있을 때 기다리던 소비자 스레드가 실행될 수 있도록 알림**.

---

## **2️⃣ `cv.wait(lock, [] { return !dataQueue.empty(); });` - 소비자가 데이터가 들어올 때까지 대기**
```cpp
cv.wait(lock, [] { return !dataQueue.empty(); });
```
### **📌 동작 원리**
- 소비자는 **큐가 비어 있으면 기다려야 함**.
- `cv.wait()`은 **조건이 충족될 때까지 현재 스레드를 대기 상태로 유지**.
- `lock`을 유지한 상태에서 `cv.wait()`를 호출하면 **자동으로 unlock 후 대기**.
- 데이터가 들어오면, `cv.notify_one()`이 호출되고, `cv.wait()`이 **자동으로 lock을 다시 걸고 실행을 재개**.

#### **📌 내부 동작 흐름**
1. `cv.wait()`은 큐가 비어 있으면 **소비자 스레드를 일시 정지**.
2. `notify_one()`이 호출되면 **대기 중이던 소비자가 깨어남**.
3. **조건이 충족되면(`!dataQueue.empty() == true`) 소비자가 실행됨.**

#### **📌 `cv.wait()`에서 람다 함수 사용**
```cpp
cv.wait(lock, [] { return !dataQueue.empty(); });
```
- 람다 함수 `[] { return !dataQueue.empty(); }`는 **큐가 비어있지 않으면 `true`를 반환**.
- `true`가 반환되면 `wait()`가 해제되고 실행이 계속됨.

---

## **3️⃣ `int value = dataQueue.front();` - 큐에서 데이터 가져오기**
```cpp
int value = dataQueue.front();
```
### **📌 동작 원리**
- `front()`는 **큐의 맨 앞(front)에 있는 데이터를 반환** (삭제 X).
- `pop()`을 호출하기 전까지 데이터는 그대로 유지됨.

💡 **`front()`는 데이터만 반환할 뿐 삭제하지 않음!**

---

## **4️⃣ `dataQueue.pop();` - 사용한 데이터 삭제**
```cpp
dataQueue.pop();
```
### **📌 동작 원리**
- `pop()`은 **큐에서 가장 앞(front)의 요소를 삭제**.
- 데이터를 소비한 후, **큐를 비우기 위해 반드시 `pop()`을 호출해야 함**.

💡 **주의: `pop()`은 데이터를 반환하지 않음! `front()`로 데이터를 가져온 후 `pop()`을 호출해야 함.**

---

# **📌 전체 코드 흐름**
### **🔹 생산자 코드**
```cpp
void producer() {
    for (int i = 1; i <= 5; i++) {
        std::unique_lock<std::mutex> lock(mtx);
        dataQueue.push(i);
        std::cout << "생산: " << i << std::endl;
        cv.notify_one();  // 소비자에게 알림
    }
}
```
1. **뮤텍스를 잠금(`lock`)**.
2. **큐에 데이터를 추가(`push(i)`)**.
3. **소비자에게 알림(`notify_one()`)**.
4. **뮤텍스 자동 해제**.

---

### **🔹 소비자 코드**
```cpp
void consumer() {
    for (int i = 1; i <= 5; i++) {
        std::unique_lock<std::mutex> lock(mtx);
        cv.wait(lock, [] { return !dataQueue.empty(); });  // 데이터가 들어올 때까지 대기
        int value = dataQueue.front();  // 데이터 가져오기
        dataQueue.pop();  // 큐에서 제거
        std::cout << "소비: " << value << std::endl;
    }
}
```
1. **뮤텍스를 잠금(`lock`)**.
2. **큐가 비어 있으면 대기(`cv.wait()`)**.
3. **큐에서 데이터를 가져옴(`front()`)**.
4. **가져온 데이터를 삭제(`pop()`)**.

---

# **📌 전체 실행 흐름**
| **순서** | **생산자 (Producer)** | **소비자 (Consumer)** |
|------|-----------------|------------------|
| 1 | `dataQueue.push(1);` | **대기 상태 (`cv.wait()`)** |
| 2 | `cv.notify_one();` | **대기 해제 후 실행** |
| 3 | **대기 (`cv.wait()`)** | `dataQueue.front();` → `dataQueue.pop();` |
| 4 | `dataQueue.push(2);` | **다시 대기 해제 후 실행** |
| ... | **반복** | **반복** |

---

# **📌 실행 결과 예시**
```
생산: 1
소비: 1
생산: 2
소비: 2
생산: 3
소비: 3
생산: 4
소비: 4
생산: 5
소비: 5
```
> ✅ **생산자가 데이터를 생성하면, 소비자가 해당 데이터를 받아 처리하는 구조**.

---

# **📌 핵심 정리**
| 코드 | 설명 |
|------|------|
| `dataQueue.push(i);` | **큐에 데이터 추가 (생산자)** |
| `cv.notify_one();` | **대기 중인 소비자 스레드를 깨움** |
| `cv.wait(lock, [] { return !dataQueue.empty(); });` | **큐가 비어있으면 소비자 스레드는 대기** |
| `dataQueue.front();` | **큐의 맨 앞 데이터를 가져옴 (삭제 X)** |
| `dataQueue.pop();` | **가져온 데이터를 큐에서 제거** |

---

# **📌 추가 최적화**
## **1. `cv.notify_all();` 사용**
```cpp
cv.notify_all();
```
- **여러 개의 소비자 스레드를 동시에 깨울 수 있음**.

## **2. `std::condition_variable_any`**
- `std::condition_variable`은 `std::unique_lock<std::mutex>`만 지원하지만,  
  `std::condition_variable_any`는 **커스텀 락을 사용할 수 있음**.

---

# **📌 결론**
- **생산자는 데이터를 생성하고, 소비자는 대기 후 데이터를 처리**.
- `std::queue`는 **FIFO(First In, First Out) 방식으로 데이터 저장**.
- `std::condition_variable`을 사용하면 **CPU 부하 없이 스레드 간 협력 가능**.

---

✅ **이제 생산자-소비자 패턴이 이해되셨나요?**  
추가 질문이 있으면 언제든지 알려주세요! 🚀

<br>
<br>
<br>

### **C++에서 `std::thread` vs `std::async` 비교**
C++에서 **멀티스레딩(`std::thread`)과 비동기 프로그래밍(`std::async`)** 은 각각 다른 목적과 장점이 있습니다.  
Python에서는 **GIL(Global Interpreter Lock) 때문에 `asyncio`가 멀티스레딩보다 더 효율적**이지만,  
C++에서는 **상황에 따라 `std::thread`와 `std::async`를 선택해야 합니다**.

---

# **📌 `std::thread` vs `std::async` 주요 차이점**
| **특징** | **`std::thread`** | **`std::async`** |
|-----------|-----------------|-----------------|
| **실행 방식** | 명시적으로 스레드를 생성하고 관리해야 함 | 내부적으로 스레드를 관리 (자동) |
| **동기화 필요 여부** | 공유 데이터를 보호하기 위해 `std::mutex` 필요 | 자동으로 결과를 관리 (`std::future`) |
| **스레드 수** | 개발자가 직접 관리 | 런타임이 최적화 |
| **예외 처리** | 직접 try-catch 필요 | `std::future`가 예외를 전달 |
| **사용 예제** | 실시간 센서 데이터 처리, ROS2 멀티스레드 노드 | CPU 바운드 작업, 비동기 요청 처리 |
| **적합한 경우** | **스레드 간 직접적인 데이터 공유**가 필요한 경우 | **병렬로 실행하고 결과를 기다려야 하는 경우** |

---

# **1️⃣ `std::thread` - 직접적인 멀티스레딩 관리**
### **📌 언제 사용해야 하나?**
✅ **여러 개의 작업을 동시에 실행하면서, 스레드 간 직접적인 데이터 공유가 필요할 때.**  
- 여러 센서 데이터를 동시에 처리하는 경우.
- 네트워크 요청을 병렬로 처리하는 경우.
- ROS2의 `MultiThreadedExecutor`를 활용할 때.

---

### **🔹 `std::thread` 기본 예제**
```cpp
#include <iostream>
#include <thread>

void task(int id) {
    std::cout << "Thread " << id << " 실행 중!" << std::endl;
}

int main() {
    std::thread t1(task, 1);
    std::thread t2(task, 2);

    t1.join();
    t2.join();

    return 0;
}
```
🔹 **출력 결과 (실행 순서는 랜덤)**
```
Thread 1 실행 중!
Thread 2 실행 중!
```
💡 `std::thread`를 사용하면 **완전히 독립적인 스레드에서 실행됨**.

---

### **🔹 `std::thread`에서 데이터 동기화 문제 (Race Condition)**
```cpp
#include <iostream>
#include <thread>

int counter = 0;

void increment() {
    for (int i = 0; i < 1000000; i++) {
        counter++;  // 💥 데이터 경합 (Race Condition) 발생 가능
    }
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);

    t1.join();
    t2.join();

    std::cout << "최종 카운트: " << counter << std::endl;  // 예상값과 다를 수 있음!
    return 0;
}
```
🔹 **출력 결과 (일관되지 않음)**
```
최종 카운트: 1345789 (항상 2000000이 아닐 수도 있음!)
```
💡 **해결 방법 → `std::mutex`로 동기화**
```cpp
std::mutex mtx;
void increment() {
    for (int i = 0; i < 1000000; i++) {
        std::lock_guard<std::mutex> lock(mtx); // 동기화
        counter++;
    }
}
```

---

# **2️⃣ `std::async` - 비동기적으로 작업 실행**
### **📌 언제 사용해야 하나?**
✅ **병렬로 실행해야 하지만, 스레드 관리를 직접 하고 싶지 않을 때.**  
- 파일 다운로드 후 자동으로 처리해야 하는 경우.
- CPU 집중 연산(예: AI 모델 실행, 수학 연산)을 수행할 때.
- ROS2에서 복잡한 비동기 작업을 실행해야 할 때.

---

### **🔹 `std::async` 기본 예제**
```cpp
#include <iostream>
#include <future>

int computeSquare(int x) {
    return x * x;
}

int main() {
    std::future<int> result = std::async(computeSquare, 5);
    
    std::cout << "결과: " << result.get() << std::endl;  // `get()`을 호출할 때까지 대기
    return 0;
}
```
🔹 **출력 결과**
```
결과: 25
```
💡 **자동으로 스레드를 생성하며, `get()`을 호출하기 전까지 실행 결과를 기다림.**

---

### **🔹 `std::async`에서 `std::future` 활용**
```cpp
#include <iostream>
#include <future>

int longTask() {
    std::this_thread::sleep_for(std::chrono::seconds(2));
    return 42;
}

int main() {
    std::future<int> result = std::async(std::launch::async, longTask);

    std::cout << "비동기 작업 실행 중..." << std::endl;
    int value = result.get();  // 여기서 결과를 기다림
    std::cout << "결과: " << value << std::endl;

    return 0;
}
```
🔹 **출력 결과**
```
비동기 작업 실행 중...
(2초 후) 결과: 42
```
💡 `std::async`를 사용하면 **스레드 관리가 자동화되며, `get()`을 호출하면 결과를 가져올 때까지 대기**.

---

# **3️⃣ `std::thread` vs `std::async` 언제 사용해야 할까?**
| 🚀 **상황** | 🧵 **`std::thread`** | 🔄 **`std::async`** |
|-------------------|-----------------|-----------------|
| **스레드 직접 관리 필요** | ✅ | ❌ |
| **병렬로 실행 & 결과 기다림** | ❌ | ✅ |
| **공유 데이터 접근 (뮤텍스 필요)** | ✅ | ❌ |
| **IO / 네트워크 요청** | ❌ | ✅ |
| **CPU 연산 (AI, 수학 계산)** | ❌ | ✅ |
| **ROS2 MultiThreadedExecutor 활용** | ✅ | ❌ |

---

# **4️⃣ Python에서 `asyncio`를 선호하는 이유**
### **🚀 Python `asyncio` vs C++ `std::async`**
Python에서는 **멀티스레딩보다 `asyncio`가 더 빠른 이유**는 다음과 같습니다.

| **특징** | **C++ (`std::async`)** | **Python (`asyncio`)** |
|-----------|-----------------|-----------------|
| **GIL (Global Interpreter Lock)** | 없음 | 있음 (멀티스레딩 비효율적) |
| **IO 바운드 작업 (네트워크, 파일)** | `std::async`로 가능 | `asyncio`로 최적화 |
| **CPU 바운드 작업 (AI, 연산)** | 멀티스레딩/멀티프로세싱 | `multiprocessing` 필요 |

💡 **Python에서는 GIL 때문에 `asyncio`가 멀티스레딩보다 더 효율적이지만, C++에서는 `std::async`와 `std::thread` 모두 빠르게 실행됨**.

---

# **📌 결론**
| **선택 기준** | **추천 방식** |
|--------------|-------------|
| **멀티스레딩이 필요 & 직접 제어해야 함** | ✅ `std::thread` |
| **결과를 기다려야 하지만 직접 관리하고 싶지 않음** | ✅ `std::async` |
| **공유 데이터가 많고 동기화가 필요함** | ✅ `std::thread + std::mutex` |
| **비동기 연산 & IO 작업 (네트워크, 파일)** | ✅ `std::async` |

✅ **C++에서는 `std::thread`는 직접 제어가 필요하지만, `std::async`는 자동으로 최적화되므로 더 편리함!**  
Python에서는 GIL 때문에 **`asyncio`가 `threading`보다 빠르지만**, C++에서는 두 방식 모두 강력한 성능을 제공함.

💡 **ROS2에서 멀티스레딩을 사용할 경우 `rclcpp::executors::MultiThreadedExecutor`를 활용하는 것이 더 효과적!**

이해되셨나요? 추가 질문이 있다면 언제든지 물어보세요! 🚀

<br>
<br>
<br>

### **왜 `최종 카운트` 값이 2000000이 아닐까? (Race Condition 발생 이유)**

```cpp
#include <iostream>
#include <thread>

int counter = 0;  // 공유 변수

void increment() {
    for (int i = 0; i < 1000000; i++) {
        counter++;  // 💥 데이터 경합 (Race Condition) 발생 가능
    }
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);

    t1.join();
    t2.join();

    std::cout << "최종 카운트: " << counter << std::endl;
    return 0;
}
```
---

## **📌 문제 발생 원인**
- `counter++` 연산이 **원자적(atomic)이지 않음**.
- 두 개의 스레드(`t1`, `t2`)가 동시에 `counter++`를 실행하면서 **Race Condition(경쟁 상태)** 발생.
- 결과적으로, **일부 증가 연산이 손실(lost update)되면서 `counter` 값이 2000000보다 작아짐**.

---

## **📌 `counter++`가 원자적이지 않은 이유**
```cpp
counter++;  // 실제로는 3단계로 실행됨:
```
1. **메모리에서 `counter` 값을 읽음 (load)**  
   ```
   register = counter;   // 예: register = 100
   ```
2. **값을 증가시킴 (increment)**  
   ```
   register = register + 1;   // 예: register = 101
   ```
3. **새 값을 메모리에 저장 (store)**  
   ```
   counter = register;   // counter = 101
   ```

---

## **📌 Race Condition 발생 과정**
### **💥 두 개의 스레드가 같은 `counter` 값을 읽고 증가시키면...?**
| 시간 | **t1 (스레드 1)** | **t2 (스레드 2)** | **공유 변수 `counter`** |
|------|----------------|----------------|----------------|
| T1   | `counter` 값을 읽음 (100) |  | 100 |
| T2   |  | `counter` 값을 읽음 (100) | 100 |
| T3   | `counter++` 수행 (`101`) |  | 100 (t1의 증가 미반영) |
| T4   |  | `counter++` 수행 (`101`) | **101** (t1의 증가가 사라짐) |

**결과:**  
- **두 개의 증가 연산 중 하나가 사라짐!**
- **100 → 101 (원래는 102가 되어야 함!)**
- 이런 일이 반복되면 `counter` 값이 **2000000보다 작아짐**.

---

## **📌 해결 방법**
### ✅ **1. `std::mutex`로 동기화**
```cpp
#include <iostream>
#include <thread>
#include <mutex>

int counter = 0;
std::mutex mtx;

void increment() {
    for (int i = 0; i < 1000000; i++) {
        std::lock_guard<std::mutex> lock(mtx);  // 🔒 락을 사용하여 동기화
        counter++;
    }
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);

    t1.join();
    t2.join();

    std::cout << "최종 카운트: " << counter << std::endl;
    return 0;
}
```
### 🔹 **출력 결과 (항상 2000000)**
```
최종 카운트: 2000000
```
💡 **`std::mutex`를 사용하면 `counter++` 연산이 원자적으로 수행됨**  
💡 **한 스레드가 `counter++` 실행 중일 때, 다른 스레드는 대기해야 함 (lock/unlock 동작)**

---

### ✅ **2. `std::atomic` 사용 (더 빠름)**
```cpp
#include <iostream>
#include <thread>
#include <atomic>

std::atomic<int> counter(0);  // atomic 변수 사용

void increment() {
    for (int i = 0; i < 1000000; i++) {
        counter++;  // 원자적 연산
    }
}

int main() {
    std::thread t1(increment);
    std::thread t2(increment);

    t1.join();
    t2.join();

    std::cout << "최종 카운트: " << counter << std::endl;
    return 0;
}
```
### 🔹 **출력 결과 (항상 2000000)**
```
최종 카운트: 2000000
```
💡 **`std::atomic<int>`을 사용하면 `counter++` 연산이 자동으로 원자적(atomic) 실행됨**  
💡 **`mutex`보다 더 빠르게 실행됨 (락이 필요 없음!)**

---

## **📌 결론**
| 해결 방법 | 코드 | 성능 | 복잡도 |
|-----------|------|------|------|
| **`std::mutex` 사용** | `std::lock_guard<std::mutex>` | 🚀 느림 (락 오버헤드 있음) | 중간 |
| **`std::atomic<int>` 사용** | `std::atomic<int>` | ⚡ 더 빠름 (락 없음) | 쉬움 |

✅ **간단한 숫자 증가 연산은 `std::atomic`을 사용하면 빠름!**  
✅ **여러 개의 변수를 동시에 보호해야 한다면 `std::mutex`가 필요함!**

---

💡 **이제 `counter++`가 왜 2000000이 아닐 수도 있는지 이해되셨나요?**  
추가 질문이 있으면 언제든지 알려주세요! 🚀

<br>
<br>
<br>

## **📌 `rclcpp::executors::MultiThreadedExecutor` 상세 설명 및 예제**
---
### **1️⃣ `rclcpp::executors::MultiThreadedExecutor`란?**
- **ROS2에서 여러 개의 콜백(Callback)을 동시에 실행할 수 있도록 하는 멀티스레딩 Executor**.
- 여러 개의 노드, 타이머, 퍼블리셔, 서브스크라이버가 동시에 실행될 때 성능을 향상시킬 수 있음.
- ROS2의 **`SingleThreadedExecutor`** 는 한 번에 하나의 콜백만 실행하지만, **`MultiThreadedExecutor`** 는 여러 개의 콜백을 **병렬로 실행** 가능.

💡 **사용 목적:**  
- 고속 데이터 수집 (센서, 카메라, LiDAR 등)
- 여러 개의 주제를 동시에 처리
- 실시간 제어 시스템
- ROS2 기반의 로봇 제어 및 자율 주행

---

## **2️⃣ `SingleThreadedExecutor` vs `MultiThreadedExecutor` 차이**
### **1) `SingleThreadedExecutor`**
```cpp
rclcpp::executors::SingleThreadedExecutor executor;
executor.add_node(node);
executor.spin();  // 하나의 콜백만 실행 (멀티스레딩 X)
```
✅ **장점**: 코드가 간단하고 동기적 실행이 보장됨  
❌ **단점**: 여러 개의 콜백이 대기해야 하므로 성능 저하 가능

---

### **2) `MultiThreadedExecutor`**
```cpp
rclcpp::executors::MultiThreadedExecutor executor;
executor.add_node(node);
executor.spin();  // 여러 개의 콜백을 병렬 실행 (멀티스레딩 O)
```
✅ **장점**: 여러 개의 콜백이 동시에 실행되어 성능 향상  
❌ **단점**: 동기화(뮤텍스) 문제 발생 가능 (공유 데이터 접근 시 주의 필요)

---

## **3️⃣ 기본 예제: `MultiThreadedExecutor`를 이용한 멀티스레딩 타이머**
💡 **여러 개의 타이머가 동시에 실행됨**

```cpp
#include "rclcpp/rclcpp.hpp"
#include <chrono>
#include <thread>

class MultiThreadedNode : public rclcpp::Node {
public:
    MultiThreadedNode() : Node("multi_threaded_node") {
        // 1초마다 실행되는 타이머 1
        timer1_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 1 실행"); });

        // 2초마다 실행되는 타이머 2
        timer2_ = this->create_wall_timer(
            std::chrono::seconds(2),
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 2 실행"); });
    }

private:
    rclcpp::TimerBase::SharedPtr timer1_;
    rclcpp::TimerBase::SharedPtr timer2_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedNode>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();  // 멀티스레드 실행

    rclcpp::shutdown();
    return 0;
}
```
**🔹 실행 결과 (동시에 실행됨)**
```
[INFO] [timer1]: 타이머 1 실행
[INFO] [timer2]: 타이머 2 실행
[INFO] [timer1]: 타이머 1 실행
[INFO] [timer1]: 타이머 1 실행
[INFO] [timer2]: 타이머 2 실행
```
💡 **`SingleThreadedExecutor`를 사용하면 `타이머 2`가 `타이머 1`의 실행을 기다려야 하지만, `MultiThreadedExecutor`를 사용하면 동시에 실행됨.**

---

## **4️⃣ `MultiThreadedExecutor`를 이용한 퍼블리셔-서브스크라이버**
💡 **서브스크라이버와 타이머가 동시에 실행됨**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MultiThreadedPubSub : public rclcpp::Node {
public:
    MultiThreadedPubSub() : Node("multi_threaded_pubsub") {
        // 퍼블리셔 생성
        publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);

        // 1초마다 메시지를 퍼블리싱
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() {
                auto message = std_msgs::msg::String();
                message.data = "Hello from ROS2!";
                publisher_->publish(message);
                RCLCPP_INFO(this->get_logger(), "퍼블리싱: %s", message.data.c_str());
            });

        // 서브스크라이버 생성
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "chatter", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            });
    }

private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedPubSub>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();  // 멀티스레드 실행

    rclcpp::shutdown();
    return 0;
}
```
**🔹 실행 결과**
```
[INFO] 퍼블리싱: Hello from ROS2!
[INFO] 수신: Hello from ROS2!
[INFO] 퍼블리싱: Hello from ROS2!
[INFO] 수신: Hello from ROS2!
```
💡 **퍼블리셔와 서브스크라이버가 독립적으로 실행되므로 지연 없이 병렬로 동작**.

---

## **5️⃣ 멀티 노드 실행 (두 개의 노드를 동시에 실행)**
💡 **두 개의 노드를 같은 Executor에서 실행할 수 있음**

```cpp
#include "rclcpp/rclcpp.hpp"

class NodeA : public rclcpp::Node {
public:
    NodeA() : Node("node_a") {
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() { RCLCPP_INFO(this->get_logger(), "Node A 실행"); });
    }

private:
    rclcpp::TimerBase::SharedPtr timer_;
};

class NodeB : public rclcpp::Node {
public:
    NodeB() : Node("node_b") {
        timer_ = this->create_wall_timer(
            std::chrono::seconds(2),
            [this]() { RCLCPP_INFO(this->get_logger(), "Node B 실행"); });
    }

private:
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto nodeA = std::make_shared<NodeA>();
    auto nodeB = std::make_shared<NodeB>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(nodeA);
    executor.add_node(nodeB);
    executor.spin();  // 멀티스레드 실행

    rclcpp::shutdown();
    return 0;
}
```
**🔹 실행 결과 (병렬 실행)**
```
[INFO] Node A 실행
[INFO] Node B 실행
[INFO] Node A 실행
[INFO] Node A 실행
[INFO] Node B 실행
```
💡 **`SingleThreadedExecutor`를 사용하면 한 노드가 실행될 때 다른 노드는 대기해야 하지만, `MultiThreadedExecutor`는 동시에 실행 가능!**

---

## **📌 정리**
| **기능** | **`SingleThreadedExecutor`** | **`MultiThreadedExecutor`** |
|-----------|-----------------|-----------------|
| **콜백 실행 방식** | 한 번에 하나씩 실행 | 여러 개 동시에 실행 |
| **실행 속도** | 느림 (대기 시간 발생) | 빠름 (동시 실행 가능) |
| **멀티 노드 실행** | 순차 실행 | 병렬 실행 |
| **추천 사용 사례** | 간단한 노드, 순차 실행 필요할 때 | 실시간 데이터 처리, 고속 센서 데이터 |

---

✅ **이제 `MultiThreadedExecutor`가 무엇인지 이해되셨나요?**  
추가 질문이 있으면 언제든지 알려주세요! 🚀

<br>
<br>
<br>

## **📌 ROS2의 Callback Group (콜백 그룹) 상세 설명 및 예제**
---
### **1️⃣ Callback Group이란?**
- **ROS2에서 여러 개의 콜백을 실행할 때, 실행 순서를 제어하는 기능**.
- `SingleThreadedExecutor`에서는 한 번에 하나의 콜백만 실행하지만,  
  `MultiThreadedExecutor`를 사용할 때 여러 개의 콜백이 동시에 실행될 수 있음.
- **콜백 그룹을 사용하면, 특정 콜백들만 병렬 실행되도록 설정 가능**.

✅ **Callback Group을 사용해야 하는 이유**
1. **서브스크라이버 & 퍼블리셔의 실행을 동시에 처리할 때**  
2. **노드 내에서 특정 콜백만 멀티스레딩을 활성화하고 싶을 때**  
3. **공유 리소스를 사용하는 콜백을 그룹화하여 동시 실행을 방지하고 싶을 때**  

---

## **2️⃣ Callback Group 없이 실행되는 경우**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class NoCallbackGroupNode : public rclcpp::Node {
public:
    NoCallbackGroupNode() : Node("no_callback_group_node") {
        // 서브스크라이버 생성
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "topic", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            });

        // 1초마다 실행되는 타이머
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() {
                RCLCPP_INFO(this->get_logger(), "타이머 실행 중...");
            });
    }

private:
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<NoCallbackGroupNode>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();  // 멀티스레딩 실행

    rclcpp::shutdown();
    return 0;
}
```
🔹 **출력 예시**
```
[INFO] 타이머 실행 중...
[INFO] 수신: Hello ROS2
[INFO] 타이머 실행 중...
[INFO] 수신: Hello ROS2
```
- `MultiThreadedExecutor`를 사용해도 **타이머와 서브스크라이버가 같은 스레드에서 실행될 수도 있음**.
- 콜백 그룹을 설정하지 않으면 **모든 콜백이 기본 그룹에서 실행됨**.

---

## **3️⃣ Callback Group을 이용한 멀티스레딩 실행**
💡 **콜백 그룹을 사용하면, 특정 콜백만 병렬 실행할 수 있음**.

```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class CallbackGroupNode : public rclcpp::Node {
public:
    CallbackGroupNode() : Node("callback_group_node") {
        // ✅ 콜백 그룹 생성 (Mutually Exclusive: 이 그룹 내 콜백은 순차 실행)
        callback_group_1_ = this->create_callback_group(rclcpp::CallbackGroupType::MutuallyExclusive);
        callback_group_2_ = this->create_callback_group(rclcpp::CallbackGroupType::Reentrant);

        // ✅ 콜백 그룹을 지정하여 서브스크라이버 생성
        rclcpp::SubscriptionOptions options;
        options.callback_group = callback_group_1_;  // 이 콜백 그룹에 속함

        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "topic", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            }, options);

        // ✅ 콜백 그룹을 지정하여 타이머 생성
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() {
                RCLCPP_INFO(this->get_logger(), "타이머 실행 중...");
            },
            callback_group_2_  // 이 콜백 그룹에 속함
        );
    }

private:
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
    rclcpp::TimerBase::SharedPtr timer_;
    rclcpp::CallbackGroup::SharedPtr callback_group_1_;
    rclcpp::CallbackGroup::SharedPtr callback_group_2_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<CallbackGroupNode>();

    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();  // 멀티스레딩 실행

    rclcpp::shutdown();
    return 0;
}
```

🔹 **출력 예시 (병렬 실행됨!)**
```
[INFO] 타이머 실행 중...
[INFO] 수신: Hello ROS2
[INFO] 타이머 실행 중...
[INFO] 수신: Hello ROS2
```
- **타이머는 `callback_group_2_` 에 속해 있으므로 서브스크라이버와 동시에 실행됨**.
- `MutuallyExclusive` 그룹(`callback_group_1_`)의 콜백은 순차 실행됨.
- `Reentrant` 그룹(`callback_group_2_`)의 콜백은 병렬 실행됨.

---

## **4️⃣ Callback Group의 종류**
### **📌 1. `MutuallyExclusive` (상호 배제)**
```cpp
auto callback_group = this->create_callback_group(rclcpp::CallbackGroupType::MutuallyExclusive);
```
✅ **특징**  
- 같은 그룹에 있는 콜백은 **하나씩만 실행됨**.
- **공유 자원이 있는 경우 사용** (예: 동일한 변수를 수정하는 콜백).
- **타이머와 서브스크라이버가 동시에 실행되지 않도록 제한 가능**.

---

### **📌 2. `Reentrant` (재진입 가능)**
```cpp
auto callback_group = this->create_callback_group(rclcpp::CallbackGroupType::Reentrant);
```
✅ **특징**  
- 같은 그룹에 있는 콜백도 **동시에 실행 가능**.
- **데이터 충돌이 없는 경우 사용** (예: 단순히 메시지를 읽기만 하는 콜백).
- **최대 성능을 끌어내려면 Reentrant 그룹을 활용**.

---

## **5️⃣ Callback Group을 활용한 퍼블리셔 & 서브스크라이버**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class PubSubCallbackGroupNode : public rclcpp::Node {
public:
    PubSubCallbackGroupNode() : Node("pubsub_callback_group_node") {
        // ✅ 퍼블리셔와 서브스크라이버를 서로 다른 그룹에 배치
        callback_group_sub_ = this->create_callback_group(rclcpp::CallbackGroupType::MutuallyExclusive);
        callback_group_pub_ = this->create_callback_group(rclcpp::CallbackGroupType::Reentrant);

        // ✅ 서브스크라이버 생성
        rclcpp::SubscriptionOptions sub_options;
        sub_options.callback_group = callback_group_sub_;
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "topic", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            }, sub_options);

        // ✅ 퍼블리셔 생성
        publisher_ = this->create_publisher<std_msgs::msg::String>("topic", 10);

        // ✅ 타이머를 이용해 퍼블리싱
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() {
                auto message = std_msgs::msg::String();
                message.data = "Hello from ROS2!";
                publisher_->publish(message);
                RCLCPP_INFO(this->get_logger(), "퍼블리싱: %s", message.data.c_str());
            },
            callback_group_pub_  // 퍼블리싱은 병렬 실행
        );
    }

private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
    rclcpp::TimerBase::SharedPtr timer_;
    rclcpp::CallbackGroup::SharedPtr callback_group_sub_;
    rclcpp::CallbackGroup::SharedPtr callback_group_pub_;
};
```
💡 **퍼블리셔는 `Reentrant`, 서브스크라이버는 `MutuallyExclusive`를 사용하여 성능과 안정성을 모두 확보!**

---

## **📌 정리**
| Callback Group 유형 | 실행 방식 | 사용 예제 |
|----------------|----------------|-----------|
| `MutuallyExclusive` | 같은 그룹 내 콜백은 하나씩 실행 | 공유 변수 접근, 데이터 충돌 방지 |
| `Reentrant` | 같은 그룹 내 콜백도 병렬 실행 가능 | 성능 최적화, 병렬 메시지 처리 |

✅ **이제 Callback Group을 통해 멀티스레딩을 더 효과적으로 제어할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 알려주세요! 😊

<br>
<br>
<br>

## **📌 해당 코드 문법 분석**
```cpp
[this](const std_msgs::msg::String::SharedPtr msg) {
    RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
}
```
이 구문은 **람다 함수(lambda function)** 를 이용하여 ROS2의 **서브스크라이버 콜백(callback) 함수** 를 정의하는 방식입니다.

---

## **1️⃣ 전체적인 문법 구조**
```cpp
[this](const std_msgs::msg::String::SharedPtr msg) {
    RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
}
```
| **구문** | **설명** |
|------|------------------|
| `[this]` | **캡처 리스트** (현재 클래스 객체의 멤버 함수 & 변수 접근 가능) |
| `(const std_msgs::msg::String::SharedPtr msg)` | **매개변수** (ROS2에서 메시지를 수신할 때 전달됨) |
| `{ ... }` | **람다 함수 본체** (메시지를 받아 실행할 코드) |

---

## **2️⃣ `[this]` → 캡처 리스트 (Capture List)**
```cpp
[this](const std_msgs::msg::String::SharedPtr msg) {
```
- **`[this]`** → 현재 클래스(`this` 포인터)를 캡처하여 람다 함수 내에서 클래스의 멤버 함수와 변수를 사용할 수 있도록 함.
- **왜 필요할까?**
  - C++의 람다 함수는 기본적으로 클래스 멤버에 직접 접근할 수 없음.
  - `[this]` 를 사용하면 현재 객체의 **`this` 포인터** 를 람다 함수 내부에서 사용할 수 있음.
- **만약 `[this]`가 없다면?**  
  - `this->get_logger()` 호출이 불가능하여 컴파일 오류 발생.

💡 **즉, 람다 함수가 현재 클래스(`this` 객체)에 있는 멤버 함수를 사용할 수 있도록 해줌!**

---

## **3️⃣ `(const std_msgs::msg::String::SharedPtr msg)` → 함수 매개변수**
```cpp
(const std_msgs::msg::String::SharedPtr msg)
```
- **ROS2에서 메시지를 수신하면, 해당 메시지가 `msg` 매개변수로 전달됨**.
- **`std_msgs::msg::String::SharedPtr`** 은 ROS2의 스마트 포인터(`std::shared_ptr`) 형식의 메시지 타입.
  - **`std::shared_ptr<T>`** 는 **동적 할당된 객체를 여러 곳에서 공유할 수 있는 스마트 포인터**.
  - `msg` 는 `std_msgs::msg::String` 타입의 메시지를 가리킴.

💡 **즉, `msg`는 ROS2 퍼블리셔가 보낸 문자열 메시지를 가리키는 스마트 포인터!**

---

## **4️⃣ `{ RCLCPP_INFO(...) }` → 실행 코드**
```cpp
{
    RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
}
```
이 코드 블록은 메시지를 받아서 실행하는 **콜백 함수의 본체** 입니다.

### **📌 `RCLCPP_INFO(...)`**
```cpp
RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
```
- **ROS2의 로그 출력 함수** (`INFO` 수준 로그)
- **형식:** `RCLCPP_INFO(LOGGER, FORMAT, ARGUMENTS...)`
  - `this->get_logger()` → 현재 노드의 로그 시스템을 가져옴.
  - `"수신: %s"` → 문자열 포맷 (`printf` 스타일).
  - `msg->data.c_str()` → `msg->data` (std::string 타입)를 C 스타일 문자열(`const char*`)로 변환.

💡 **즉, ROS2에서 메시지를 수신하면 해당 메시지를 로그로 출력하는 코드!**

---

## **📌 코드 전체 예제**
💡 **이제 전체 코드를 봐보자!**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class ExampleSubscriber : public rclcpp::Node {
public:
    ExampleSubscriber() : Node("example_subscriber") {
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "topic", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {  // ✅ 람다 콜백
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            });
    }

private:
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<ExampleSubscriber>();
    rclcpp::spin(node);  // 노드 실행
    rclcpp::shutdown();
    return 0;
}
```

🔹 **출력 예시 (퍼블리셔가 `"Hello ROS2"` 메시지를 보냈을 때)**
```
[INFO] 수신: Hello ROS2
```
---

## **📌 최종 정리**
| 구문 | 설명 |
|------|----------------------|
| `[this]` | 현재 클래스의 멤버 함수 & 변수 사용 가능 |
| `std_msgs::msg::String::SharedPtr msg` | ROS2 메시지를 가리키는 스마트 포인터 |
| `msg->data.c_str()` | ROS2 메시지의 `std::string` 데이터를 `const char*`로 변환 |
| `RCLCPP_INFO(...)` | ROS2 로그 출력 (INFO 수준) |

✅ **이제 이 코드가 어떻게 동작하는지 이해되셨나요?** 🚀  
추가 질문이 있다면 언제든지 물어보세요! 😊

<br>
<br>
<br>
<br>
<br>

# **6. ROS2 C++ 환경 설정 및 패키지 빌드**

ROS2에서 C++을 사용하려면 **개발 환경을 설정하고, 패키지를 생성하고, 빌드 및 코드 스타일을 관리하는 과정**이 필요합니다.  
이번 강의에서는 **Ubuntu에서 ROS2 Humble/Foxy를 설치하고, C++ 기반의 ROS2 패키지를 생성하여 빌드하는 방법**을 단계별로 설명합니다.

---

## **1️⃣ ROS2 개발 환경 설치 (Ubuntu + ROS2 Humble/Foxy)**

💡 **ROS2를 설치하려면 먼저 Ubuntu 환경이 필요합니다.**  
ROS2는 Ubuntu LTS 버전(22.04, 20.04)에서 안정적으로 동작하며, 가장 많이 사용되는 **Humble (22.04)** 또는 **Foxy (20.04)** 를 설치할 수 있습니다.

---

### **🔹 Ubuntu 22.04에서 ROS2 Humble 설치 (추천)**
```bash
# 1. 시스템 업데이트
sudo apt update && sudo apt upgrade -y

# 2. ROS2 설치를 위한 패키지 추가
sudo apt install -y curl gnupg2 lsb-release

# 3. ROS2 패키지 저장소 추가
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key | sudo apt-key add -
echo "deb http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/ros2.list

# 4. 패키지 리스트 업데이트 후 ROS2 Humble 설치
sudo apt update
sudo apt install -y ros-humble-desktop

# 5. 환경 변수 설정 (bash 기준)
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

✅ **설치 확인**
```bash
ros2 --version  # 설치된 ROS2 버전 확인
```

✅ **TurtleBot3 시뮬레이터 실행 (테스트)**
```bash
ros2 run turtlesim turtlesim_node  # ROS2 GUI 실행
```
---

### **🔹 Ubuntu 20.04에서 ROS2 Foxy 설치**
💡 Foxy도 기본 설치 과정은 Humble과 비슷하지만 패키지 이름이 다릅니다.
```bash
sudo apt update
sudo apt install -y ros-foxy-desktop
```
💡 이후 환경 설정 (`source /opt/ros/foxy/setup.bash`) 과정은 Humble과 동일합니다.

---

## **2️⃣ C++ 기반 ROS2 패키지 생성 (ament_cmake 사용)**

### **📌 1. 워크스페이스 생성**
```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
```
- `ros2_ws/` → ROS2 패키지를 저장할 **워크스페이스** (Workspace)
- `src/` → 모든 ROS2 패키지가 들어가는 폴더

---

### **📌 2. C++ 패키지 생성 (`ament_cmake` 사용)**
```bash
cd ~/ros2_ws/src
ros2 pkg create --build-type ament_cmake my_cpp_pkg --dependencies rclcpp std_msgs
```

✅ **위 명령어 실행 시 생성되는 주요 파일**
```
my_cpp_pkg/
├── CMakeLists.txt   # 빌드 설정 파일 (ament_cmake 사용)
├── package.xml      # 패키지 메타정보 (이름, 의존성 등)
├── src/             # C++ 소스 코드 폴더
└── include/         # C++ 헤더 파일 폴더
```

✅ **의미**
- `--build-type ament_cmake` → `ament_cmake` 빌드 시스템을 사용
- `--dependencies rclcpp std_msgs` → `rclcpp` (ROS2 C++ API) 및 `std_msgs` (표준 메시지) 의존성 추가

---

## **3️⃣ colcon 빌드 시스템 소개 및 빌드 방법**
### **📌 colcon이란?**
- ROS2의 공식 빌드 시스템으로 **여러 개의 패키지를 한 번에 빌드**할 수 있음.
- `catkin_make` (ROS1) 대신 `colcon build`를 사용함.

### **📌 colcon 설치 (Ubuntu)**
```bash
sudo apt install -y python3-colcon-common-extensions
```

---

### **📌 ROS2 패키지 빌드 (`colcon build`)**
```bash
cd ~/ros2_ws
colcon build --packages-select my_cpp_pkg
```

✅ **빌드 완료 후 환경 설정**
```bash
source install/setup.bash
```

✅ **설치된 패키지 확인**
```bash
ros2 pkg list | grep my_cpp_pkg
```
---

## **4️⃣ C++ 코드 스타일 가이드 (`ament_lint`, `clang-format`)**
ROS2에서는 **코드 스타일을 통일하고, 코드 품질을 유지하기 위해 `ament_lint`와 `clang-format`을 사용**할 수 있습니다.

### **📌 1. `ament_lint` 설치**
```bash
sudo apt install -y python3-ament-lint python3-ament-cmake
```

✅ **코드 스타일 검사를 실행하는 방법**
```bash
cd ~/ros2_ws
colcon test --packages-select my_cpp_pkg
```

✅ **결과 예시**
```
test results for my_cpp_pkg: 1 test passed, 0 tests failed
```

---

### **📌 2. `clang-format`을 사용한 코드 자동 정리**
💡 **C++ 코드 스타일을 정리하는 도구**
```bash
sudo apt install -y clang-format
```

✅ **자동 정리 실행**
```bash
cd ~/ros2_ws/src/my_cpp_pkg
clang-format -i src/*.cpp include/*.hpp
```
---

## **📌 최종 정리**
| 작업 | 명령어 |
|------|-------------------------------|
| ROS2 설치 | `sudo apt install ros-humble-desktop` |
| 워크스페이스 생성 | `mkdir -p ~/ros2_ws/src` |
| C++ 패키지 생성 | `ros2 pkg create --build-type ament_cmake my_cpp_pkg` |
| 패키지 빌드 | `colcon build --packages-select my_cpp_pkg` |
| 코드 스타일 검사 | `colcon test --packages-select my_cpp_pkg` |
| 코드 자동 정리 | `clang-format -i src/*.cpp include/*.hpp` |

✅ **이제 ROS2에서 C++ 패키지를 생성하고 빌드하는 방법을 이해하셨나요?** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊

<br>
<br>
<br>

# **📌 CMakeLists.txt 와 package.xml 상세 설명 및 코드 예제**

ROS2에서 **C++ 패키지를 생성하고 빌드할 때 핵심적인 두 파일**이 있습니다:
1. `CMakeLists.txt` → 패키지 빌드 설정 (CMake 사용)
2. `package.xml` → 패키지 메타정보 (이름, 의존성, 버전 등)

---

# **1️⃣ CMakeLists.txt 문법 및 예제**
`CMakeLists.txt`는 **패키지를 빌드하기 위한 CMake 스크립트 파일**입니다.  
ROS2에서는 **`ament_cmake` 빌드 시스템을 사용**하여 C++ 코드를 빌드합니다.

---

## **📌 CMakeLists.txt 예제 코드**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_cpp_pkg)

# ament_cmake 사용
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)

# 실행 파일 추가
add_executable(my_node src/my_node.cpp)

# 실행 파일에 필요한 라이브러리 연결
ament_target_dependencies(my_node rclcpp std_msgs)

# 설치 경로 설정
install(TARGETS
  my_node
  DESTINATION lib/${PROJECT_NAME}
)

# 빌드 시스템 설정
ament_package()
```

---

## **📌 CMakeLists.txt 코드 분석**
### **🔹 1. CMake 최소 버전 및 프로젝트 이름**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_cpp_pkg)
```
- **`cmake_minimum_required(VERSION 3.8)`** → CMake 최소 버전 지정 (ROS2에서 요구하는 최소 버전)
- **`project(my_cpp_pkg)`** → 현재 프로젝트 이름 설정 (ROS2 패키지명과 동일하게 설정)

---

### **🔹 2. `ament_cmake` 및 의존성 패키지 찾기**
```cmake
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
```
- `find_package()` → 필요한 ROS2 패키지 (`ament_cmake`, `rclcpp`, `std_msgs`) 를 찾음
- `REQUIRED` → 필수적으로 필요함을 의미 (`없으면 빌드 실패`)

💡 **이 패키지들은 ROS2의 핵심 라이브러리**
  - `ament_cmake` → ROS2의 CMake 빌드 시스템
  - `rclcpp` → ROS2의 C++ API
  - `std_msgs` → 기본 메시지 타입

---

### **🔹 3. 실행 파일 추가 및 라이브러리 연결**
```cmake
add_executable(my_node src/my_node.cpp)
ament_target_dependencies(my_node rclcpp std_msgs)
```
- `add_executable(my_node src/my_node.cpp)`  
  → `my_node` 라는 실행 파일을 `src/my_node.cpp` 로부터 생성
- `ament_target_dependencies(my_node rclcpp std_msgs)`  
  → `rclcpp`, `std_msgs` 라이브러리를 실행 파일(`my_node`)에 연결

💡 **즉, `my_node` 실행 파일이 ROS2 C++ 라이브러리를 사용할 수 있도록 설정됨**

---

### **🔹 4. 빌드된 실행 파일을 설치할 위치 지정**
```cmake
install(TARGETS
  my_node
  DESTINATION lib/${PROJECT_NAME}
)
```
- **설치 경로 설정**  
  → `lib/my_cpp_pkg/my_node` 에 실행 파일이 배치됨.

---

### **🔹 5. `ament_package()` 호출**
```cmake
ament_package()
```
- **ROS2의 `ament_cmake` 빌드 시스템을 사용하기 위해 반드시 추가해야 함!**
- `ament_package()` 없으면 `colcon build` 실행 시 오류 발생

---

# **2️⃣ package.xml 문법 및 예제**
`package.xml`은 **ROS2 패키지의 메타데이터** (이름, 버전, 의존성 등)를 정의하는 XML 파일입니다.

---

## **📌 package.xml 예제 코드**
```xml
<?xml version="1.0"?>
<package format="3">
  <name>my_cpp_pkg</name>
  <version>0.0.1</version>
  <description>ROS2 C++ 패키지 예제</description>
  <maintainer email="your_email@example.com">Your Name</maintainer>
  <license>Apache-2.0</license>

  <!-- 빌드 시 필요한 패키지 -->
  <buildtool_depend>ament_cmake</buildtool_depend>

  <!-- 실행 시 필요한 패키지 -->
  <depend>rclcpp</depend>
  <depend>std_msgs</depend>

  <!-- 테스트를 위한 패키지 -->
  <test_depend>ament_lint_auto</test_depend>
  <test_depend>ament_lint_common</test_depend>

  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```

---

## **📌 package.xml 코드 분석**
### **🔹 1. 패키지 기본 정보**
```xml
<package format="3">
  <name>my_cpp_pkg</name>
  <version>0.0.1</version>
  <description>ROS2 C++ 패키지 예제</description>
  <maintainer email="your_email@example.com">Your Name</maintainer>
  <license>Apache-2.0</license>
</package>
```
- `<name>` → 패키지명 (`ros2 pkg list`에서 확인 가능)
- `<version>` → 버전 정보
- `<description>` → 패키지 설명
- `<maintainer>` → 패키지 유지보수자 정보
- `<license>` → 라이선스 정보 (ROS2 기본값: `Apache-2.0`)

💡 **라이선스 예시**
- **`Apache-2.0`** (추천)
- `MIT`
- `GPLv3`

---

### **🔹 2. 패키지 의존성 설정**
#### **(1) 빌드 도구 의존성 (`buildtool_depend`)**
```xml
<buildtool_depend>ament_cmake</buildtool_depend>
```
- ROS2에서 `colcon build`를 사용할 때 **CMake 빌드 시스템을 이용하도록 설정**.

#### **(2) 실행 시 필요한 의존성 (`depend`)**
```xml
<depend>rclcpp</depend>
<depend>std_msgs</depend>
```
- `rclcpp` → ROS2 C++ API
- `std_msgs` → 표준 메시지 타입

#### **(3) 테스트 의존성 (`test_depend`)**
```xml
<test_depend>ament_lint_auto</test_depend>
<test_depend>ament_lint_common</test_depend>
```
- 코드 스타일 검사 (`ament_lint_auto`, `ament_lint_common`)

---

### **🔹 3. 빌드 시스템 설정**
```xml
<export>
  <build_type>ament_cmake</build_type>
</export>
```
- `ament_cmake` 빌드 시스템을 사용하도록 설정.

---

# **📌 최종 정리**
| 파일 | 역할 |
|------|------------------------------|
| `CMakeLists.txt` | C++ 코드 빌드 및 실행 파일 설정 |
| `package.xml` | 패키지 메타데이터 및 의존성 설정 |

✅ **이제 ROS2에서 C++ 패키지를 빌드하는 전체 과정을 이해할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊

<br>
<br>
<br>
<br>

# **7. ROS2 노드(Node) 프로그래밍**
ROS2에서 **노드(Node)** 는 로봇의 기능을 독립적인 프로그램 단위로 분리하여 실행하는 기본 단위입니다.  
이번 강의에서는 **C++ 기반의 ROS2 노드를 생성하고 실행하는 방법 및 노드의 라이프사이클을 다루는 `LifecycleNode` 개념**을 설명합니다.

---

# **1️⃣ `rclcpp::Node` 클래스를 활용한 기본 노드 생성**
### **📌 ROS2에서 노드란?**
- **노드(Node)** 는 ROS2에서 실행되는 **독립적인 실행 단위**입니다.
- 예를 들어, **센서 데이터 처리, 모터 제어, 경로 계획** 등의 기능을 각각의 노드로 구현할 수 있음.
- **C++에서는 `rclcpp::Node` 클래스를 상속받아 노드를 생성**할 수 있음.

---

### **🔹 기본 노드 예제 (C++ 노드 생성)**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {  // 노드 이름 설정
        RCLCPP_INFO(this->get_logger(), "ROS2 노드가 실행되었습니다!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);  // ROS2 초기화
    auto node = std::make_shared<MyNode>();  // 노드 객체 생성
    rclcpp::spin(node);  // 노드 실행 (콜백 처리)
    rclcpp::shutdown();  // 종료 시 ROS2 정리
    return 0;
}
```

---

### **📌 코드 분석**
| 코드 | 설명 |
|------|------|
| `class MyNode : public rclcpp::Node` | ROS2 노드를 생성하는 C++ 클래스 |
| `Node("my_node")` | 노드의 이름을 `"my_node"`로 설정 |
| `rclcpp::init(argc, argv);` | ROS2 시스템 초기화 |
| `auto node = std::make_shared<MyNode>();` | 노드 객체를 생성 (스마트 포인터 사용) |
| `rclcpp::spin(node);` | 노드를 실행하며 **콜백 함수 처리** (무한 루프) |
| `rclcpp::shutdown();` | 노드 종료 및 리소스 정리 |

✅ **이제 기본적인 ROS2 노드를 생성하고 실행할 수 있습니다!**

---

# **2️⃣ ROS2 패키지에서 C++ 노드 실행하기 (`ros2 run`)**
### **📌 ROS2 패키지에 위 노드 추가**
ROS2에서 C++ 노드를 실행하려면 `CMakeLists.txt` 및 `package.xml` 파일을 수정해야 합니다.

---

### **🔹 `CMakeLists.txt`에 실행 파일 추가**
```cmake
add_executable(my_node src/my_node.cpp)
ament_target_dependencies(my_node rclcpp)
install(TARGETS
  my_node
  DESTINATION lib/${PROJECT_NAME}
)
```
✅ **의미**
- `add_executable(my_node src/my_node.cpp)` → `my_node.cpp`를 실행 파일로 생성
- `ament_target_dependencies(my_node rclcpp)` → `rclcpp` 라이브러리를 연결
- `install(TARGETS my_node DESTINATION lib/${PROJECT_NAME})` → 실행 파일을 ROS2의 실행 경로에 설치

---

### **🔹 패키지 빌드 후 실행**
```bash
cd ~/ros2_ws
colcon build --packages-select my_cpp_pkg
source install/setup.bash
ros2 run my_cpp_pkg my_node
```
✅ **출력 결과**
```
[INFO] [my_node]: ROS2 노드가 실행되었습니다!
```
💡 **이제 ROS2 패키지에서 C++ 노드를 실행할 수 있습니다!**

---

# **3️⃣ 노드의 라이프사이클 (`LifecycleNode`)**
### **📌 `LifecycleNode`란?**
- ROS2에서 **노드의 상태를 관리하고, 특정 이벤트에 따라 동작을 변경하는 기능**을 제공.
- 예를 들어, **센서를 초기화하고 데이터를 처리하다가 종료할 때 정리 작업을 수행하는 과정**을 포함.

---

## **📌 노드의 상태 (Lifecycle States)**
| 상태 | 설명 |
|------|------|
| `unconfigured` | 노드가 생성되었지만 아직 구성되지 않음 |
| `inactive` | 노드가 구성되었지만 활성화되지 않음 |
| `active` | 노드가 실행 중이며 데이터를 처리 가능 |
| `finalized` | 노드가 종료됨 (정리 완료) |

---

### **🔹 `LifecycleNode` 구현 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "rclcpp_lifecycle/lifecycle_node.hpp"

class MyLifecycleNode : public rclcpp_lifecycle::LifecycleNode {
public:
    MyLifecycleNode() : LifecycleNode("lifecycle_node") {}

    // 노드가 구성될 때 실행되는 함수
    rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn on_configure(const rclcpp_lifecycle::State &) {
        RCLCPP_INFO(get_logger(), "노드가 구성되었습니다!");
        return rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn::SUCCESS;
    }

    // 노드가 활성화될 때 실행되는 함수
    rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn on_activate(const rclcpp_lifecycle::State &) {
        RCLCPP_INFO(get_logger(), "노드가 활성화되었습니다!");
        return rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn::SUCCESS;
    }

    // 노드가 비활성화될 때 실행되는 함수
    rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn on_deactivate(const rclcpp_lifecycle::State &) {
        RCLCPP_INFO(get_logger(), "노드가 비활성화되었습니다!");
        return rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn::SUCCESS;
    }

    // 노드가 종료될 때 실행되는 함수
    rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn on_cleanup(const rclcpp_lifecycle::State &) {
        RCLCPP_INFO(get_logger(), "노드가 정리되었습니다!");
        return rclcpp_lifecycle::node_interfaces::LifecycleNodeInterface::CallbackReturn::SUCCESS;
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MyLifecycleNode>();
    rclcpp::executors::SingleThreadedExecutor executor;
    executor.add_node(node->get_node_base_interface());
    executor.spin();
    rclcpp::shutdown();
    return 0;
}
```

---

### **📌 코드 분석**
| 함수 | 설명 |
|------|---------------------------|
| `on_configure()` | 노드가 설정될 때 호출됨 |
| `on_activate()` | 노드가 활성화될 때 호출됨 |
| `on_deactivate()` | 노드가 비활성화될 때 호출됨 |
| `on_cleanup()` | 노드가 종료될 때 호출됨 |

✅ **이제 ROS2의 `LifecycleNode`를 이해하고 활용할 수 있습니다!**

---

# **📌 최종 정리**
| 개념 | 설명 |
|------|--------------------------|
| `rclcpp::Node` | 기본 ROS2 C++ 노드 생성 |
| `ros2 run` | 패키지에서 노드 실행 |
| `LifecycleNode` | 노드의 상태를 관리하는 구조 |

✅ **이제 ROS2 C++ 노드를 만들고 실행할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊

<br>
<br>
<br>
<br>

# **8. ROS2 통신 기초 (C++ 적용)**  
ROS2에서 **노드(Node) 간의 데이터 교환**을 위해 **토픽(Topic), 서비스(Service), 액션(Action)** 기반의 다양한 통신 방식을 제공합니다.  
이번 강의에서는 **C++을 이용하여 ROS2의 다양한 통신 기법을 예제와 함께 설명**합니다.  

---

# **📌 1️⃣ 토픽(Topic) 기반 통신**  
**토픽(Topic)** 은 ROS2의 기본적인 **비동기(Asynchronous) 데이터 교환 방식**입니다.  
- **퍼블리셔(Publisher)**: 데이터를 송신하는 역할 (`rclcpp::Publisher`)  
- **서브스크라이버(Subscriber)**: 데이터를 수신하는 역할 (`rclcpp::Subscription`)  
- **QoS (Quality of Service)**: 신뢰성, 유지 시간 등 네트워크 설정 가능 (`rclcpp::QoS`)  

---

## **🔹 퍼블리셔 예제 (`rclcpp::Publisher`)**  
💡 **토픽을 통해 "Hello ROS2!" 메시지를 1초마다 전송하는 노드**  

```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class SimplePublisher : public rclcpp::Node {
public:
    SimplePublisher() : Node("simple_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            [this]() {
                auto message = std_msgs::msg::String();
                message.data = "Hello ROS2!";
                RCLCPP_INFO(this->get_logger(), "퍼블리싱: %s", message.data.c_str());
                publisher_->publish(message);
            });
    }

private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<SimplePublisher>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **주요 기능**  
- `create_publisher<std_msgs::msg::String>("chatter", 10)` → `chatter` 토픽에 **문자열 메시지를 송신**  
- 1초마다 **"Hello ROS2!" 메시지 전송**  
- `publish(message);` → 퍼블리싱 실행  

---

## **🔹 서브스크라이버 예제 (`rclcpp::Subscription`)**  
💡 **퍼블리셔가 보낸 메시지를 수신하는 서브스크라이버 노드**  

```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class SimpleSubscriber : public rclcpp::Node {
public:
    SimpleSubscriber() : Node("simple_subscriber") {
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "chatter", 10,
            [this](const std_msgs::msg::String::SharedPtr msg) {
                RCLCPP_INFO(this->get_logger(), "수신: %s", msg->data.c_str());
            });
    }

private:
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<SimpleSubscriber>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **주요 기능**  
- `create_subscription<std_msgs::msg::String>("chatter", 10, callback)`  
  → `chatter` 토픽의 데이터를 수신하고 **콜백 함수에서 출력**  
- `msg->data.c_str()` → 받은 메시지를 출력  

---

# **📌 2️⃣ QoS (Quality of Service) 설정**  
💡 **네트워크 품질을 조정하는 방법 (기본값은 `keep_last(10)`)**  

### **📌 QoS 예제**
```cpp
rclcpp::QoS qos_profile(10);
qos_profile.reliability(RMW_QOS_POLICY_RELIABILITY_RELIABLE);
qos_profile.durability(RMW_QOS_POLICY_DURABILITY_TRANSIENT_LOCAL);
auto publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", qos_profile);
```
✅ **QoS 설정 의미**  
- `reliability(RELIABLE)` → 데이터 손실 없이 **확실하게 전달**  
- `durability(TRANSIENT_LOCAL)` → **이전 메시지를 새로운 구독자에게 제공**  

---

# **📌 3️⃣ 서비스 (Service) 통신**  
**서비스(Service) 통신** 은 **요청(Request)과 응답(Response)이 있는 동기(Synchronous) 통신 방식**입니다.  
- **서비스 서버 (rclcpp::Service)** → 요청을 받고 응답을 처리  
- **서비스 클라이언트 (rclcpp::Client)** → 요청을 보내고 응답을 받음  

---

## **🔹 서비스 서버 예제 (`rclcpp::Service`)**  
💡 **두 개의 정수를 받아 더한 결과를 반환하는 서비스 서버 노드**  

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class AddTwoIntsServer : public rclcpp::Node {
public:
    AddTwoIntsServer() : Node("add_two_ints_server") {
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            [this](const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
                   std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) {
                response->sum = request->a + request->b;
                RCLCPP_INFO(this->get_logger(), "요청: %ld + %ld = %ld", request->a, request->b, response->sum);
            });
    }

private:
    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};
```
✅ **요청을 받아 두 정수를 더한 후 응답을 반환!**  

---

## **🔹 서비스 클라이언트 예제 (`rclcpp::Client`)**  
💡 **두 정수를 더해달라고 요청하는 서비스 클라이언트 노드**  

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class AddTwoIntsClient : public rclcpp::Node {
public:
    AddTwoIntsClient() : Node("add_two_ints_client") {
        client_ = this->create_client<example_interfaces::srv::AddTwoInts>("add_two_ints");
    }

    void send_request(int64_t a, int64_t b) {
        auto request = std::make_shared<example_interfaces::srv::AddTwoInts::Request>();
        request->a = a;
        request->b = b;

        auto future = client_->async_send_request(request);
        auto response = future.get();
        RCLCPP_INFO(this->get_logger(), "응답: %ld", response->sum);
    }

private:
    rclcpp::Client<example_interfaces::srv::AddTwoInts>::SharedPtr client_;
};
```
✅ **클라이언트가 `a=3, b=5` 요청 → 서버가 `sum=8` 응답 반환!**

---

# **📌 4️⃣ 액션(Action) 기반 통신**
**액션(Action) 통신** 은 **서비스와 비슷하지만, 중간 진행 상태를 반환할 수 있는 비동기(Asynchronous) 통신 방식**입니다.  
- **액션 서버 (`rclcpp_action::Server`)** → 요청을 받고, 실행 상태를 주기적으로 반환한 후 응답을 처리  
- **액션 클라이언트 (`rclcpp_action::Client`)** → 요청을 보내고, 실행 상태를 지속적으로 모니터링  

---

### **📌 액션 서버 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "rclcpp_action/rclcpp_action.hpp"
#include "example_interfaces/action/fibonacci.hpp"

class FibonacciActionServer : public rclcpp::Node {
public:
    FibonacciActionServer() : Node("fibonacci_action_server") {
        action_server_ = rclcpp_action::create_server<example_interfaces::action::Fibonacci>(
            this, "fibonacci",
            [](auto, auto) { return rclcpp_action::GoalResponse::ACCEPT_AND_EXECUTE; },
            [](auto) { return rclcpp_action::CancelResponse::ACCEPT; },
            [this](const std::shared_ptr<rclcpp_action::ServerGoalHandle<example_interfaces::action::Fibonacci>> goal_handle) {
                // 액션 실행 로직
            });
    }

private:
    rclcpp_action::Server<example_interfaces::action::Fibonacci>::SharedPtr action_server_;
};
```
✅ **액션은 진행 상태를 주기적으로 반환할 수 있음!**

---

✅ **이제 ROS2에서 C++을 활용하여 토픽, 서비스, 액션을 구현할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>

# **9. ROS2 메시지 타입과 C++에서의 활용**
ROS2에서 **노드 간 통신을 위해 다양한 메시지 타입**을 제공합니다.  
이번 강의에서는 **기본 메시지 타입 사용법, 커스텀 메시지 생성, 메시지 직렬화/역직렬화 방법**을 다룹니다.

---

## **1️⃣ 기본 메시지 타입 (`std_msgs`, `sensor_msgs`, `geometry_msgs`)**
### **📌 기본 메시지 패키지**
ROS2에서는 표준 메시지를 제공하는 패키지가 있습니다.

| **메시지 패키지** | **설명** | **예제 메시지 타입** |
|-----------------|---------|---------------------|
| `std_msgs` | 기본 데이터 타입 | `std_msgs::msg::String`, `std_msgs::msg::Int32` |
| `sensor_msgs` | 센서 데이터 | `sensor_msgs::msg::LaserScan`, `sensor_msgs::msg::Image` |
| `geometry_msgs` | 좌표 및 변환 | `geometry_msgs::msg::Pose`, `geometry_msgs::msg::Twist` |

---

### **🔹 `std_msgs` 예제: 문자열 메시지**
💡 **"Hello ROS2" 문자열을 퍼블리싱하는 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class StringPublisher : public rclcpp::Node {
public:
    StringPublisher() : Node("string_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            [this]() {
                auto message = std_msgs::msg::String();
                message.data = "Hello ROS2!";
                RCLCPP_INFO(this->get_logger(), "퍼블리싱: %s", message.data.c_str());
                publisher_->publish(message);
            });
    }

private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
✅ **`std_msgs::msg::String`을 사용하여 문자열 메시지를 전송**

---

### **🔹 `sensor_msgs` 예제: `LaserScan` (LiDAR 데이터)**
💡 **가상 LiDAR 데이터를 퍼블리싱하는 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "sensor_msgs/msg/laser_scan.hpp"

class LaserScanPublisher : public rclcpp::Node {
public:
    LaserScanPublisher() : Node("laser_scan_publisher") {
        publisher_ = this->create_publisher<sensor_msgs::msg::LaserScan>("scan", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            [this]() {
                auto scan_msg = sensor_msgs::msg::LaserScan();
                scan_msg.header.stamp = this->get_clock()->now();
                scan_msg.header.frame_id = "laser_frame";
                scan_msg.angle_min = -1.57;
                scan_msg.angle_max = 1.57;
                scan_msg.range_min = 0.1;
                scan_msg.range_max = 10.0;
                scan_msg.ranges = {1.0, 2.0, 3.0, 4.0};  // 가상 거리 데이터

                RCLCPP_INFO(this->get_logger(), "LiDAR 데이터 퍼블리싱");
                publisher_->publish(scan_msg);
            });
    }

private:
    rclcpp::Publisher<sensor_msgs::msg::LaserScan>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
✅ **센서 데이터를 표현하는 `sensor_msgs::msg::LaserScan` 메시지 사용**

---

### **🔹 `geometry_msgs` 예제: `Pose` (위치 및 자세 정보)**
💡 **로봇의 위치와 자세(Pose)를 퍼블리싱하는 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "geometry_msgs/msg/pose.hpp"

class PosePublisher : public rclcpp::Node {
public:
    PosePublisher() : Node("pose_publisher") {
        publisher_ = this->create_publisher<geometry_msgs::msg::Pose>("robot_pose", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            [this]() {
                auto pose_msg = geometry_msgs::msg::Pose();
                pose_msg.position.x = 1.0;
                pose_msg.position.y = 2.0;
                pose_msg.position.z = 0.0;
                pose_msg.orientation.x = 0.0;
                pose_msg.orientation.y = 0.0;
                pose_msg.orientation.z = 0.0;
                pose_msg.orientation.w = 1.0;

                RCLCPP_INFO(this->get_logger(), "로봇 위치 퍼블리싱");
                publisher_->publish(pose_msg);
            });
    }

private:
    rclcpp::Publisher<geometry_msgs::msg::Pose>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
✅ **`geometry_msgs::msg::Pose`를 이용하여 로봇의 위치 및 자세 데이터 전송**

---

## **2️⃣ 커스텀 메시지 생성 (`rosidl_generator_cpp`)**
💡 **사용자가 직접 새로운 메시지 타입을 정의하여 사용할 수 있음**

---

### **📌 1. `msg` 폴더에 메시지 파일 생성**
💡 **ROS2 패키지의 `msg/` 폴더 안에 `MyMessage.msg` 파일을 생성**
```bash
mkdir -p ~/ros2_ws/src/my_pkg/msg
cd ~/ros2_ws/src/my_pkg/msg
touch MyMessage.msg
```
**🔹 `msg/MyMessage.msg` 파일 내용**
```
int32 id
string message
float32 value
```
✅ **`id` (정수), `message` (문자열), `value` (실수) 필드를 포함하는 커스텀 메시지**

---

### **📌 2. `CMakeLists.txt`에 메시지 빌드 설정 추가**
```cmake
find_package(rosidl_default_generators REQUIRED)

add_message_files(
  FILES
  MyMessage.msg
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
)
```
✅ **커스텀 메시지를 자동으로 C++ 및 Python 코드로 변환하도록 설정**

---

### **📌 3. `package.xml`에 메시지 의존성 추가**
```xml
<build_depend>rosidl_default_generators</build_depend>
<exec_depend>rosidl_default_runtime</exec_depend>
```
✅ **ROS2의 메시지 생성을 위한 `rosidl_default_generators` 추가**

---

### **📌 4. 패키지 빌드**
```bash
cd ~/ros2_ws
colcon build --packages-select my_pkg
source install/setup.bash
```
✅ **커스텀 메시지가 빌드 완료되면 C++에서 사용 가능!**

---

## **3️⃣ 메시지 직렬화 및 역직렬화 (`rclcpp::Serialization`)**
💡 **메시지를 바이너리 데이터로 변환하여 전송하거나 저장할 수 있음**

---

### **📌 1. 메시지 직렬화 (Serialize)**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"
#include "rclcpp/serialization.hpp"

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    std_msgs::msg::String msg;
    msg.data = "Hello ROS2!";

    rclcpp::Serialization<std_msgs::msg::String> serializer;
    rclcpp::SerializedMessage serialized_msg;
    serializer.serialize_message(&msg, &serialized_msg);

    RCLCPP_INFO(rclcpp::get_logger("serializer"), "직렬화 완료!");
    return 0;
}
```
✅ **`serializer.serialize_message()`를 사용하여 메시지를 바이너리 형태로 변환**

---

### **📌 2. 메시지 역직렬화 (Deserialize)**
```cpp
std_msgs::msg::String deserialized_msg;
serializer.deserialize_message(&serialized_msg, &deserialized_msg);
RCLCPP_INFO(rclcpp::get_logger("serializer"), "역직렬화된 데이터: %s", deserialized_msg.data.c_str());
```
✅ **역직렬화를 통해 원본 데이터 복구 가능!**

---

## **📌 최종 정리**
| 기능 | 메시지 타입 | 예제 |
|------|------------|------|
| **기본 메시지 사용** | `std_msgs`, `sensor_msgs`, `geometry_msgs` | `std_msgs::msg::String`, `sensor_msgs::msg::LaserScan` |
| **커스텀 메시지 생성** | `rosidl_generator_cpp` | `MyMessage.msg` |
| **메시지 직렬화** | `rclcpp::Serialization` | `serialize_message()` |

✅ **이제 ROS2에서 다양한 메시지 타입을 C++로 활용할 수 있습니다!** 🚀  



<br>
<br>
<br>
<br>

### **📌 ROS2에서 메시지 직렬화(Serialization)와 역직렬화(Deserialization)를 사용하는 이유**

**💡 직렬화(Serialization)와 역직렬화(Deserialization)는 메시지를 바이너리 데이터로 변환하여 저장하거나 네트워크를 통해 효율적으로 전송할 때 사용됩니다.**  

직렬화된 데이터는 **더 작은 크기로 변환되어 빠르게 전송되거나 저장될 수 있으며, 역직렬화를 통해 다시 원래의 메시지 객체로 변환할 수 있습니다.**  

---

## **1️⃣ 언제 직렬화와 역직렬화를 사용할까?**
| **사용 사례** | **설명** |
|-------------|----------------------------------------------|
| **메시지를 파일에 저장** | ROS2 메시지를 로그 파일이나 데이터베이스에 저장 |
| **네트워크 전송 최적화** | 여러 메시지를 하나의 바이너리 데이터로 묶어 네트워크를 통해 빠르게 전송 |
| **ROS2 노드 간 메시지 공유** | 직접 ROS2 퍼블리셔-서브스크라이버가 아닌, **UDP/TCP 소켓 또는 공유 메모리를 통해 데이터를 주고받을 때** |
| **멀티 프로세스 간 데이터 공유** | `rclcpp::Serialization`을 사용하여 **다른 프로세스나 머신에서도 동일한 메시지를 복원 가능** |

---

## **2️⃣ 메시지를 파일에 저장하고 다시 불러오기 (직렬화 & 역직렬화 활용 예제)**
💡 **ROS2에서 메시지를 JSON/바이너리 파일로 저장하고 다시 불러오는 예제**

### **🔹 메시지 직렬화 후 파일 저장**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"
#include "rclcpp/serialization.hpp"
#include <fstream>

void save_message_to_file(const std_msgs::msg::String &msg, const std::string &filename) {
    rclcpp::Serialization<std_msgs::msg::String> serializer;
    rclcpp::SerializedMessage serialized_msg;
    
    // 메시지 직렬화
    serializer.serialize_message(&msg, &serialized_msg);

    // 직렬화된 데이터를 파일에 저장
    std::ofstream out_file(filename, std::ios::binary);
    out_file.write(reinterpret_cast<const char*>(serialized_msg.get_rcl_serialized_message().buffer),
                   serialized_msg.get_rcl_serialized_message().buffer_length);
    out_file.close();

    RCLCPP_INFO(rclcpp::get_logger("serializer"), "메시지를 파일에 저장: %s", filename.c_str());
}

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    // 메시지 생성
    std_msgs::msg::String msg;
    msg.data = "Hello ROS2 Serialization!";

    // 메시지 파일 저장
    save_message_to_file(msg, "ros2_message.bin");

    rclcpp::shutdown();
    return 0;
}
```
✅ **`serialize_message()`를 사용하여 ROS2 메시지를 바이너리 파일로 저장**  
✅ **이후 언제든지 역직렬화를 통해 데이터를 복원할 수 있음**  

---

### **🔹 저장된 메시지를 파일에서 불러와 역직렬화**
```cpp
void load_message_from_file(std_msgs::msg::String &msg, const std::string &filename) {
    rclcpp::Serialization<std_msgs::msg::String> serializer;
    rclcpp::SerializedMessage serialized_msg;

    // 파일에서 직렬화된 데이터 읽기
    std::ifstream in_file(filename, std::ios::binary);
    if (in_file) {
        in_file.seekg(0, std::ios::end);
        std::streamsize size = in_file.tellg();
        in_file.seekg(0, std::ios::beg);

        serialized_msg.reserve(size);
        in_file.read(reinterpret_cast<char*>(serialized_msg.get_rcl_serialized_message().buffer), size);
        in_file.close();

        // 역직렬화하여 메시지 복원
        serializer.deserialize_message(&serialized_msg, &msg);

        RCLCPP_INFO(rclcpp::get_logger("serializer"), "파일에서 메시지를 로드: %s", msg.data.c_str());
    } else {
        RCLCPP_ERROR(rclcpp::get_logger("serializer"), "파일을 열 수 없습니다: %s", filename.c_str());
    }
}

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    std_msgs::msg::String msg;
    
    // 저장된 메시지를 복원
    load_message_from_file(msg, "ros2_message.bin");

    rclcpp::shutdown();
    return 0;
}
```
✅ **파일에서 데이터를 불러와 `deserialize_message()`를 이용해 복원 가능!**  
✅ **이 방법을 이용하면, ROS2 메시지를 로그 파일로 저장하여 이후 분석 가능!**  

---

## **3️⃣ 멀티 프로세스 간 메시지 공유 (공유 메모리 활용)**
💡 **ROS2 메시지를 `rclcpp::Serialization`을 이용해 직렬화한 후, 공유 메모리를 통해 다른 프로세스와 데이터 공유**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"
#include "rclcpp/serialization.hpp"
#include <sys/mman.h>
#include <fcntl.h>
#include <unistd.h>

void save_to_shared_memory(const std_msgs::msg::String &msg) {
    rclcpp::Serialization<std_msgs::msg::String> serializer;
    rclcpp::SerializedMessage serialized_msg;
    serializer.serialize_message(&msg, &serialized_msg);

    int fd = shm_open("/ros2_shared_mem", O_CREAT | O_RDWR, 0666);
    ftruncate(fd, serialized_msg.size());
    void *ptr = mmap(0, serialized_msg.size(), PROT_WRITE, MAP_SHARED, fd, 0);
    memcpy(ptr, serialized_msg.get_rcl_serialized_message().buffer, serialized_msg.size());
    munmap(ptr, serialized_msg.size());
    close(fd);

    RCLCPP_INFO(rclcpp::get_logger("serializer"), "공유 메모리에 메시지 저장!");
}

void load_from_shared_memory(std_msgs::msg::String &msg) {
    rclcpp::Serialization<std_msgs::msg::String> serializer;
    rclcpp::SerializedMessage serialized_msg;

    int fd = shm_open("/ros2_shared_mem", O_RDONLY, 0666);
    struct stat sb;
    fstat(fd, &sb);
    void *ptr = mmap(0, sb.st_size, PROT_READ, MAP_SHARED, fd, 0);
    memcpy(serialized_msg.get_rcl_serialized_message().buffer, ptr, sb.st_size);
    munmap(ptr, sb.st_size);
    close(fd);

    serializer.deserialize_message(&serialized_msg, &msg);
    RCLCPP_INFO(rclcpp::get_logger("serializer"), "공유 메모리에서 메시지 로드: %s", msg.data.c_str());
}
```
✅ **이 방법을 이용하면, ROS2 메시지를 네트워크 없이 프로세스 간 빠르게 공유 가능!**  
✅ **공유 메모리를 사용하면 데이터 복사 없이 빠르게 처리 가능!**

---

## **📌 최종 정리**
| 사용 사례 | 직렬화 필요 여부 | 설명 |
|-----------|----------------|------------------------------------|
| **ROS2 퍼블리셔-서브스크라이버** | ❌ | 기본적인 ROS2 메시지 통신 |
| **메시지를 파일로 저장** | ✅ | ROS2 데이터를 로그로 저장 후 분석 |
| **네트워크 전송 최적화** | ✅ | 메시지를 바이너리 형태로 압축 후 전송 |
| **멀티 프로세스 간 데이터 공유** | ✅ | 공유 메모리를 이용한 메시지 교환 |

✅ **이제 ROS2에서 직렬화/역직렬화가 언제 필요한지 이해되셨나요?** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **10. ROS2 TF2와 C++**
ROS2에서 **TF2 (Transform Framework 2)** 는 **로봇의 좌표 변환 및 프레임 관리**를 담당하는 필수적인 라이브러리입니다.  
이번 강의에서는 **C++을 활용하여 TF2를 사용하고, 좌표 변환을 수행하며, TF 브로드캐스터와 리스너를 구현하는 방법**을 다룹니다.  

---

# **📌 1️⃣ TF2란?**
**TF2 (Transform Framework 2)** 는 **로봇의 여러 프레임을 효율적으로 관리하고 변환하는 기능**을 제공하는 ROS2 라이브러리입니다.  
- **TF 브로드캐스터 (Broadcaster)** → 프레임의 위치 및 자세(Pose) 정보를 송신  
- **TF 리스너 (Listener)** → 브로드캐스터가 보낸 변환 정보를 수신 및 활용  
- **좌표 변환 (Coordinate Transformation)** → 특정 프레임에서 다른 프레임으로 좌표 변환 수행  

### **🔹 예제: 로봇과 센서의 관계**
- 로봇의 기본 좌표 프레임: **"base_link"**
- LiDAR 센서의 좌표 프레임: **"laser"**
- `laser`의 위치가 `base_link` 기준으로 `(x=1.0, y=0.0, z=0.2)` 라면?
  → `TF 브로드캐스터`가 **"base_link → laser"** 변환을 지속적으로 송신  
  → `TF 리스너`가 이를 받아서 **좌표 변환을 수행 가능**

---

# **📌 2️⃣ `tf2_ros::Buffer` 와 `tf2_ros::TransformListener` 사용법**
TF2에서 **변환 정보를 저장하고 관리하는 핵심 클래스**는 `tf2_ros::Buffer`와 `tf2_ros::TransformListener` 입니다.  

| **클래스** | **설명** |
|-----------|--------------------------------|
| `tf2_ros::Buffer` | 좌표 변환 데이터를 저장하고 관리 |
| `tf2_ros::TransformListener` | TF 브로드캐스터가 보낸 변환 정보를 수신 |

---

## **🔹 TF2 리스너 예제 (`tf2_ros::TransformListener`)**
💡 **"base_link" 기준으로 "laser" 프레임의 위치를 확인하는 코드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/buffer.h"
#include "tf2_ros/transform_listener.h"
#include "geometry_msgs/msg/transform_stamped.hpp"

class TFListener : public rclcpp::Node {
public:
    TFListener() : Node("tf_listener") {
        tf_buffer_ = std::make_shared<tf2_ros::Buffer>(this->get_clock());
        tf_listener_ = std::make_shared<tf2_ros::TransformListener>(*tf_buffer_);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&TFListener::lookupTransform, this));
    }

private:
    void lookupTransform() {
        try {
            geometry_msgs::msg::TransformStamped transform;
            transform = tf_buffer_->lookupTransform("base_link", "laser", tf2::TimePointZero);

            RCLCPP_INFO(this->get_logger(), "laser 좌표 (x: %f, y: %f, z: %f)",
                        transform.transform.translation.x,
                        transform.transform.translation.y,
                        transform.transform.translation.z);
        } catch (tf2::TransformException &ex) {
            RCLCPP_WARN(this->get_logger(), "TF 조회 실패: %s", ex.what());
        }
    }

    std::shared_ptr<tf2_ros::Buffer> tf_buffer_;
    std::shared_ptr<tf2_ros::TransformListener> tf_listener_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<TFListener>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **`tf2_ros::TransformListener`가 "base_link → laser" 변환 정보를 가져옴**  
✅ **TF가 없을 경우 예외 처리 (`TransformException`)를 수행하여 안전한 코드 구현**  

---

# **📌 3️⃣ 좌표 변환 및 프레임 관리 (`geometry_msgs::TransformStamped`)**
💡 **좌표 변환은 로봇의 다양한 센서 및 부품 간 위치 관계를 설정하는 데 사용됩니다.**  

| **메시지 타입** | **설명** |
|----------------|--------------------------------|
| `geometry_msgs::TransformStamped` | 두 프레임 간 변환 정보를 저장 |
| `geometry_msgs::Vector3` | 3D 공간 내 위치 (x, y, z) |
| `geometry_msgs::Quaternion` | 3D 공간 내 회전 (x, y, z, w) |

---

### **🔹 `TransformStamped` 활용 예제**
```cpp
geometry_msgs::msg::TransformStamped transform;
transform.header.stamp = this->get_clock()->now();
transform.header.frame_id = "base_link";
transform.child_frame_id = "laser";
transform.transform.translation.x = 1.0;
transform.transform.translation.y = 0.0;
transform.transform.translation.z = 0.2;

// 오일러 각도를 쿼터니언으로 변환하여 설정
tf2::Quaternion q;
q.setRPY(0, 0, 0);  // (roll, pitch, yaw)
transform.transform.rotation.x = q.x();
transform.transform.rotation.y = q.y();
transform.transform.rotation.z = q.z();
transform.transform.rotation.w = q.w();
```
✅ **`TransformStamped`를 사용하여 `base_link → laser` 변환 정의**  
✅ **`tf2::Quaternion`을 활용해 회전 정보 설정**  

---

# **📌 4️⃣ TF 브로드캐스트 및 리스너 구현**
## **🔹 TF 브로드캐스터 (`tf2_ros::TransformBroadcaster`)**
💡 **"base_link"에서 "laser" 프레임을 지속적으로 브로드캐스트하는 코드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/transform_broadcaster.h"
#include "geometry_msgs/msg/transform_stamped.hpp"
#include "tf2/LinearMath/Quaternion.h"

class TFBroadcaster : public rclcpp::Node {
public:
    TFBroadcaster() : Node("tf_broadcaster") {
        broadcaster_ = std::make_shared<tf2_ros::TransformBroadcaster>(this);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&TFBroadcaster::broadcastTransform, this));
    }

private:
    void broadcastTransform() {
        geometry_msgs::msg::TransformStamped transform;
        transform.header.stamp = this->get_clock()->now();
        transform.header.frame_id = "base_link";
        transform.child_frame_id = "laser";
        transform.transform.translation.x = 1.0;
        transform.transform.translation.y = 0.0;
        transform.transform.translation.z = 0.2;

        tf2::Quaternion q;
        q.setRPY(0, 0, 0);
        transform.transform.rotation.x = q.x();
        transform.transform.rotation.y = q.y();
        transform.transform.rotation.z = q.z();
        transform.transform.rotation.w = q.w();

        broadcaster_->sendTransform(transform);
    }

    std::shared_ptr<tf2_ros::TransformBroadcaster> broadcaster_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<TFBroadcaster>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **TF 브로드캐스터가 "base_link → laser" 변환을 1초마다 송신**  
✅ **`tf2_ros::TransformBroadcaster`를 사용하여 좌표 변환을 브로드캐스트**  

---

# **📌 최종 정리**
| 기능 | C++ 클래스/메시지 | 역할 |
|------|----------------|------------------------------|
| **TF 리스너** | `tf2_ros::TransformListener` | TF 브로드캐스터가 보낸 변환을 수신 |
| **TF 버퍼** | `tf2_ros::Buffer` | TF 데이터를 저장 및 관리 |
| **좌표 변환** | `geometry_msgs::TransformStamped` | 프레임 간 변환 정보 저장 |
| **TF 브로드캐스터** | `tf2_ros::TransformBroadcaster` | 변환 정보를 지속적으로 방송 |

✅ **이제 ROS2에서 C++을 활용한 TF2 좌표 변환을 구현할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>

**`broadcaster_->sendTransform(transform);`**  
이 코드가 **ROS2 토픽 메시지 퍼블리싱(`publish()`)과 동일한 역할을 하는지**에 대한 질문이죠?  

💡 **짧은 답변:**  
✅ **"Yes, TF 브로드캐스터는 내부적으로 ROS2 토픽 메시지(`/tf` 또는 `/tf_static`)를 퍼블리싱합니다."**  
그러나 일반적인 ROS2 토픽 퍼블리싱과는 몇 가지 차이점이 있습니다.

---

## **📌 `sendTransform()`과 `publish()` 비교**
| 기능 | 일반 ROS2 퍼블리싱 (`publish()`) | TF2 브로드캐스팅 (`sendTransform()`) |
|------|---------------------------------|----------------------------------|
| **퍼블리셔 객체** | `rclcpp::Publisher<T>::SharedPtr` | `tf2_ros::TransformBroadcaster` |
| **메시지 타입** | `std_msgs::msg::String`, `sensor_msgs::msg::LaserScan`, `geometry_msgs::msg::Pose` 등 | `geometry_msgs::msg::TransformStamped` |
| **토픽 이름** | `"chatter"`, `"scan"` 등 개발자가 지정 | **`/tf` 또는 `/tf_static` (자동 설정됨)** |
| **퍼블리싱 방식** | `publisher_->publish(msg);` | `broadcaster_->sendTransform(transform);` |
| **구독자** | 일반 ROS2 노드 | `tf2_ros::TransformListener` (TF 리스너 노드) |

### **📌 `sendTransform()` 동작 방식**
- `sendTransform()`을 호출하면 **내부적으로 `/tf` 토픽에 `geometry_msgs::msg::TransformStamped` 메시지를 자동 퍼블리싱**합니다.
- 일반적인 `publish()`와 차이점은 **토픽 이름을 직접 설정하지 않고, TF2 시스템이 자동으로 `/tf` 또는 `/tf_static`으로 관리한다는 점**입니다.

---

## **📌 실제 퍼블리싱 확인 (`ros2 topic list` & `ros2 topic echo`)**
### **✅ TF 브로드캐스터 실행 후 확인**
TF 브로드캐스터 노드를 실행한 후, 터미널에서 ROS2 토픽 리스트를 확인하면 `/tf` 또는 `/tf_static` 토픽이 자동으로 생성됩니다.

```bash
ros2 topic list
```
🔹 **출력 예시**
```
/tf
/tf_static
```
`/tf` → **시간이 변하는 동적(Dynamic) 프레임 변환 정보**  
`/tf_static` → **한 번 설정되면 변하지 않는 정적(Static) 변환 정보**

### **✅ 실제 메시지 확인**
```bash
ros2 topic echo /tf
```
🔹 **출력 예시 (`geometry_msgs::msg::TransformStamped`)**
```
transforms:
- header:
    stamp:
      sec: 1643812345
    frame_id: "base_link"
  child_frame_id: "laser"
  transform:
    translation:
      x: 1.0
      y: 0.0
      z: 0.2
    rotation:
      x: 0.0
      y: 0.0
      z: 0.0
      w: 1.0
```
✅ **즉, `sendTransform()`은 내부적으로 `/tf` 토픽에 메시지를 퍼블리싱하는 것과 동일한 역할을 수행**합니다.  

---

## **📌 정적(Static) TF 퍼블리싱 (`/tf_static`)**
💡 특정 변환이 변하지 않는 경우 **정적 TF 브로드캐스터(`StaticTransformBroadcaster`)를 사용하여 `/tf_static` 토픽으로 퍼블리싱**할 수 있습니다.

```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/static_transform_broadcaster.h"
#include "geometry_msgs/msg/transform_stamped.hpp"

class StaticTFBroadcaster : public rclcpp::Node {
public:
    StaticTFBroadcaster() : Node("static_tf_broadcaster") {
        static_broadcaster_ = std::make_shared<tf2_ros::StaticTransformBroadcaster>(this);
        broadcastStaticTransform();
    }

private:
    void broadcastStaticTransform() {
        geometry_msgs::msg::TransformStamped transform;
        transform.header.stamp = this->get_clock()->now();
        transform.header.frame_id = "map";
        transform.child_frame_id = "robot_base";
        transform.transform.translation.x = 2.0;
        transform.transform.translation.y = 3.0;
        transform.transform.translation.z = 0.0;
        transform.transform.rotation.w = 1.0;

        static_broadcaster_->sendTransform(transform);
        RCLCPP_INFO(this->get_logger(), "정적 TF 퍼블리싱 완료!");
    }

    std::shared_ptr<tf2_ros::StaticTransformBroadcaster> static_broadcaster_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<StaticTFBroadcaster>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **이 코드는 `map → robot_base` 변환을 `/tf_static` 토픽에 퍼블리싱합니다.**  
✅ **정적 변환을 사용하면 CPU 부하를 줄일 수 있음!**

---

## **📌 결론: `sendTransform()` vs 일반 ROS2 `publish()`**
| 기능 | 일반 퍼블리싱 (`publish()`) | TF2 변환 브로드캐스팅 (`sendTransform()`) |
|------|------------------|------------------|
| **사용되는 클래스** | `rclcpp::Publisher<T>` | `tf2_ros::TransformBroadcaster` |
| **메시지 타입** | `std_msgs::msg::String` 등 | `geometry_msgs::msg::TransformStamped` |
| **토픽 이름** | 개발자가 지정 | `/tf` 또는 `/tf_static` (자동) |
| **구독 방식** | 일반 ROS2 서브스크라이버 | `tf2_ros::TransformListener` |
| **사용 목적** | 센서 데이터, 상태 정보 등 일반 메시지 전송 | 좌표 변환 정보를 퍼블리싱 |

✅ **즉, `sendTransform()`은 내부적으로 `/tf` 토픽을 통해 메시지를 퍼블리싱하며, 일반적인 `publish()`와 동일한 개념이지만, TF2가 자동으로 메시지를 관리해준다는 점에서 차이가 있습니다.** 🚀


<br>
<br>
<br>
<br>

# **📌 ROS2 TF2 사용 방법 - 구체적인 예제**
ROS2에서 **TF2(Transform Framework 2)** 는 **로봇의 여러 좌표 프레임을 관리하고 변환하는 기능**을 제공합니다.  
이 강의에서는 **TF2를 활용한 프레임 관리, 변환, 브로드캐스터, 리스너 구현**을 구체적인 예제와 함께 다룹니다.

---

## **📌 1️⃣ TF2 개념 정리**
### **✅ TF2는 왜 필요한가?**
로봇 시스템에서는 여러 개의 **좌표 프레임(Frame)** 이 존재합니다.
예를 들어:
- **"base_link"** (로봇 본체)
- **"laser"** (LiDAR 센서)
- **"camera"** (카메라)

이때, **각 프레임 간의 변환(Transform)을 관리하고 좌표를 변환하는 역할을 하는 것이 TF2**입니다.

---

## **📌 2️⃣ TF2 브로드캐스터 (Transform Broadcaster)**
💡 **TF2 브로드캐스터는 특정 프레임 간의 변환 정보를 계속 송신하는 역할**을 합니다.  
예제: **"base_link" → "laser" 프레임 변환을 1초마다 브로드캐스트**

---

### **🔹 1. TF 브로드캐스터 코드 (`tf2_ros::TransformBroadcaster`)**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/transform_broadcaster.h"
#include "geometry_msgs/msg/transform_stamped.hpp"
#include "tf2/LinearMath/Quaternion.h"

class TFBroadcaster : public rclcpp::Node {
public:
    TFBroadcaster() : Node("tf_broadcaster") {
        broadcaster_ = std::make_shared<tf2_ros::TransformBroadcaster>(this);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&TFBroadcaster::broadcastTransform, this));
    }

private:
    void broadcastTransform() {
        geometry_msgs::msg::TransformStamped transform;
        transform.header.stamp = this->get_clock()->now();
        transform.header.frame_id = "base_link";
        transform.child_frame_id = "laser";
        transform.transform.translation.x = 1.0;
        transform.transform.translation.y = 0.0;
        transform.transform.translation.z = 0.2;

        tf2::Quaternion q;
        q.setRPY(0, 0, 0);  // 회전 없음
        transform.transform.rotation.x = q.x();
        transform.transform.rotation.y = q.y();
        transform.transform.rotation.z = q.z();
        transform.transform.rotation.w = q.w();

        broadcaster_->sendTransform(transform);
        RCLCPP_INFO(this->get_logger(), "base_link -> laser 변환 브로드캐스트 중...");
    }

    std::shared_ptr<tf2_ros::TransformBroadcaster> broadcaster_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<TFBroadcaster>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **1초마다 "base_link" → "laser" 변환 정보를 `/tf` 토픽으로 퍼블리싱**  
✅ **TF2는 내부적으로 `/tf` 토픽을 사용하여 모든 변환을 공유함**  

---

## **📌 3️⃣ TF2 리스너 (Transform Listener)**
💡 **TF2 리스너는 브로드캐스터가 송신한 변환 정보를 구독하고, 좌표 변환을 수행하는 역할**을 합니다.  
예제: **"laser"의 위치를 "base_link" 기준으로 가져오기**

---

### **🔹 2. TF 리스너 코드 (`tf2_ros::TransformListener`)**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/buffer.h"
#include "tf2_ros/transform_listener.h"
#include "geometry_msgs/msg/transform_stamped.hpp"

class TFListener : public rclcpp::Node {
public:
    TFListener() : Node("tf_listener") {
        tf_buffer_ = std::make_shared<tf2_ros::Buffer>(this->get_clock());
        tf_listener_ = std::make_shared<tf2_ros::TransformListener>(*tf_buffer_);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&TFListener::lookupTransform, this));
    }

private:
    void lookupTransform() {
        try {
            geometry_msgs::msg::TransformStamped transform;
            transform = tf_buffer_->lookupTransform("base_link", "laser", tf2::TimePointZero);

            RCLCPP_INFO(this->get_logger(), "laser 좌표 (x: %f, y: %f, z: %f)",
                        transform.transform.translation.x,
                        transform.transform.translation.y,
                        transform.transform.translation.z);
        } catch (tf2::TransformException &ex) {
            RCLCPP_WARN(this->get_logger(), "TF 조회 실패: %s", ex.what());
        }
    }

    std::shared_ptr<tf2_ros::Buffer> tf_buffer_;
    std::shared_ptr<tf2_ros::TransformListener> tf_listener_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<TFListener>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **TF 리스너가 `/tf` 토픽에서 "base_link" → "laser" 변환 정보를 수신**  
✅ **`lookupTransform("base_link", "laser", tf2::TimePointZero)`를 사용하여 현재 변환 값을 조회**  
✅ **조회 실패 시 `TransformException`을 처리하여 안전하게 예외 방지**

---

## **📌 4️⃣ TF2를 활용한 좌표 변환**
💡 **TF2는 특정 프레임에서 다른 프레임으로 좌표를 변환할 수 있습니다.**  
예제: **"laser" 좌표 `(x=2, y=1, z=0)`를 "base_link" 기준으로 변환하기**

---

### **🔹 3. TF2 좌표 변환 코드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "tf2_ros/buffer.h"
#include "tf2_ros/transform_listener.h"
#include "tf2_geometry_msgs/tf2_geometry_msgs.h"
#include "geometry_msgs/msg/point_stamped.hpp"

class TFTransformExample : public rclcpp::Node {
public:
    TFTransformExample() : Node("tf_transform_example") {
        tf_buffer_ = std::make_shared<tf2_ros::Buffer>(this->get_clock());
        tf_listener_ = std::make_shared<tf2_ros::TransformListener>(*tf_buffer_);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&TFTransformExample::transformPoint, this));
    }

private:
    void transformPoint() {
        try {
            geometry_msgs::msg::TransformStamped transformStamped;
            transformStamped = tf_buffer_->lookupTransform("base_link", "laser", tf2::TimePointZero);

            geometry_msgs::msg::PointStamped laser_point;
            laser_point.header.frame_id = "laser";
            laser_point.header.stamp = this->get_clock()->now();
            laser_point.point.x = 2.0;
            laser_point.point.y = 1.0;
            laser_point.point.z = 0.0;

            geometry_msgs::msg::PointStamped base_link_point;
            tf2::doTransform(laser_point, base_link_point, transformStamped);

            RCLCPP_INFO(this->get_logger(), "변환된 좌표 (x: %f, y: %f, z: %f)",
                        base_link_point.point.x, base_link_point.point.y, base_link_point.point.z);
        } catch (tf2::TransformException &ex) {
            RCLCPP_WARN(this->get_logger(), "좌표 변환 실패: %s", ex.what());
        }
    }

    std::shared_ptr<tf2_ros::Buffer> tf_buffer_;
    std::shared_ptr<tf2_ros::TransformListener> tf_listener_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
✅ **`doTransform()`을 사용하여 "laser" 기준 좌표 `(2,1,0)`를 "base_link" 기준으로 변환**  
✅ **TF2를 사용하면 여러 프레임 간의 좌표 변환을 쉽게 수행할 수 있음**

---

## **📌 최종 정리**
| 기능 | C++ 클래스/메서드 | 설명 |
|------|----------------|------------------------------|
| **TF 브로드캐스터** | `tf2_ros::TransformBroadcaster` | 프레임 변환을 `/tf` 토픽으로 송신 |
| **TF 리스너** | `tf2_ros::TransformListener` | 변환 데이터를 수신하여 저장 |
| **좌표 변환** | `tf2::doTransform()` | 특정 프레임 기준 좌표 변환 |

✅ **이제 ROS2에서 C++을 활용하여 TF2를 제대로 활용할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **11. ROS2 파라미터 서버 및 C++에서의 활용**  
ROS2에서는 **파라미터(Parameters)를 사용하여 노드의 동작을 동적으로 설정**할 수 있습니다.  
이를 통해 **하드코딩 없이 노드 실행 중에 설정값을 변경**할 수 있습니다.  
이번 강의에서는 **ROS2의 `rclcpp::Parameter`를 이용한 파라미터 선언 및 활용, 그리고 동적 업데이트(`rclcpp::ParameterEventHandler`) 방법을 구체적인 예제와 함께 설명**합니다.

---

## **📌 1️⃣ `rclcpp::Parameter`와 파라미터 선언**
### **✅ ROS2에서 파라미터란?**
- **ROS1의 파라미터 서버와 달리, ROS2에서는 각 노드가 자체적으로 파라미터를 관리**합니다.
- **파라미터는 ROS2 런타임 동안 값을 유지하며, 노드 실행 중에 변경 가능**합니다.
- 노드가 실행 중일 때, **`ros2 param set` 명령어를 사용하여 값을 수정 가능**합니다.

---

### **🔹 1. 기본 파라미터 선언 및 사용 (`declare_parameter()`)**
💡 **ROS2에서는 `declare_parameter()`를 사용하여 파라미터를 선언하고, `get_parameter()`로 값을 가져올 수 있습니다.**  

```cpp
#include "rclcpp/rclcpp.hpp"

class ParameterExample : public rclcpp::Node {
public:
    ParameterExample() : Node("parameter_example") {
        // ✅ 파라미터 선언 (기본값 지정)
        this->declare_parameter<std::string>("robot_name", "TurtleBot");
        this->declare_parameter<int>("max_speed", 5);

        // ✅ 파라미터 값 가져오기
        std::string robot_name = this->get_parameter("robot_name").as_string();
        int max_speed = this->get_parameter("max_speed").as_int();

        RCLCPP_INFO(this->get_logger(), "로봇 이름: %s", robot_name.c_str());
        RCLCPP_INFO(this->get_logger(), "최대 속도: %d", max_speed);
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<ParameterExample>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **이제 `robot_name`과 `max_speed` 파라미터를 선언하고 가져올 수 있습니다.**  
✅ **`declare_parameter()`를 사용하여 기본값을 설정할 수 있습니다.**

---

### **🔹 2. 런타임 중 파라미터 변경 (`ros2 param set`)**
노드를 실행한 후, **터미널에서 파라미터 값을 변경할 수 있습니다.**  
```bash
ros2 param set /parameter_example robot_name "RoboMaster"
ros2 param set /parameter_example max_speed 10
```
📌 **그러나 위 명령어로 값을 변경해도, 코드 내에서 즉시 반영되지 않습니다.**  
📌 이를 해결하려면 **파라미터 변경을 감지하는 기능(`rclcpp::ParameterEventHandler`)이 필요**합니다.

---

## **📌 2️⃣ 동적 파라미터 업데이트 (`rclcpp::ParameterEventHandler`)**
💡 **ROS2에서는 `rclcpp::ParameterEventHandler`를 사용하여 파라미터 변경을 실시간으로 감지하고, 업데이트할 수 있습니다.**  
이 방법을 사용하면 **노드를 다시 실행하지 않고도 설정값을 동적으로 변경**할 수 있습니다.

---

### **🔹 3. 동적 파라미터 업데이트 코드 (`rclcpp::ParameterEventHandler`)**
💡 **파라미터가 변경될 때마다 자동으로 콜백 함수가 실행되도록 설정합니다.**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "rclcpp/parameter_event_handler.hpp"

class DynamicParameterNode : public rclcpp::Node {
public:
    DynamicParameterNode() : Node("dynamic_parameter_node") {
        // ✅ 파라미터 선언 (기본값 포함)
        this->declare_parameter<std::string>("robot_name", "TurtleBot");
        this->declare_parameter<int>("max_speed", 5);

        // ✅ 현재 파라미터 값 출력
        RCLCPP_INFO(this->get_logger(), "초기 로봇 이름: %s", 
                    this->get_parameter("robot_name").as_string().c_str());
        RCLCPP_INFO(this->get_logger(), "초기 최대 속도: %d", 
                    this->get_parameter("max_speed").as_int());

        // ✅ 파라미터 이벤트 핸들러 생성
        param_event_handler_ = std::make_shared<rclcpp::ParameterEventHandler>(this);

        // ✅ 특정 파라미터의 변경을 감지하는 콜백 등록
        robot_name_cb_handle_ = param_event_handler_->add_parameter_callback(
            "robot_name",
            [this](const rclcpp::Parameter &param) {
                RCLCPP_INFO(this->get_logger(), "로봇 이름 변경: %s", param.as_string().c_str());
            });

        max_speed_cb_handle_ = param_event_handler_->add_parameter_callback(
            "max_speed",
            [this](const rclcpp::Parameter &param) {
                RCLCPP_INFO(this->get_logger(), "최대 속도 변경: %d", param.as_int());
            });
    }

private:
    std::shared_ptr<rclcpp::ParameterEventHandler> param_event_handler_;
    std::shared_ptr<rclcpp::ParameterCallbackHandle> robot_name_cb_handle_;
    std::shared_ptr<rclcpp::ParameterCallbackHandle> max_speed_cb_handle_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<DynamicParameterNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```

✅ **파라미터가 변경될 때마다 자동으로 콜백 함수 실행!**  
✅ **`rclcpp::ParameterEventHandler`를 사용하여 특정 파라미터의 변경을 감지할 수 있음!**  

---

### **🔹 4. 실행 후 동적 파라미터 변경**
```bash
ros2 run my_package dynamic_parameter_node
```
✅ **초기 파라미터 값 출력**
```
[INFO] [dynamic_parameter_node]: 초기 로봇 이름: TurtleBot
[INFO] [dynamic_parameter_node]: 초기 최대 속도: 5
```

✅ **터미널에서 값 변경 후 자동 업데이트**
```bash
ros2 param set /dynamic_parameter_node robot_name "RoboMaster"
ros2 param set /dynamic_parameter_node max_speed 20
```
✅ **변경된 값이 실시간으로 적용됨**
```
[INFO] [dynamic_parameter_node]: 로봇 이름 변경: RoboMaster
[INFO] [dynamic_parameter_node]: 최대 속도 변경: 20
```
💡 **이제 노드를 다시 실행하지 않아도, 동적으로 파라미터 변경이 가능합니다!** 🚀

---

## **📌 3️⃣ 노드 내부에서 파라미터 업데이트 (`set_parameter()`)**
💡 **ROS2 노드 내부에서 직접 파라미터 값을 수정할 수도 있습니다.**
```cpp
this->set_parameter(rclcpp::Parameter("robot_name", "SuperBot"));
this->set_parameter(rclcpp::Parameter("max_speed", 15));
```
✅ **이 코드를 실행하면, 현재 노드의 파라미터가 변경됩니다.**

---

## **📌 최종 정리**
| 기능 | 사용 함수 | 설명 |
|------|---------|------------------------------|
| **파라미터 선언** | `declare_parameter()` | 노드가 실행될 때 파라미터를 선언 |
| **파라미터 가져오기** | `get_parameter()` | 현재 파라미터 값을 조회 |
| **파라미터 변경** | `set_parameter()` | 노드 내부에서 파라미터 값 변경 |
| **동적 파라미터 감지** | `rclcpp::ParameterEventHandler` | 파라미터가 변경될 때 콜백 실행 |

✅ **이제 ROS2에서 C++을 활용하여 동적으로 파라미터를 관리할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊



<br>
<br>
<br>

**📌 네, ROS2의 `launch` 파일과 `YAML` 파일을 사용하여 노드의 파라미터를 설정하는 것은 바로 위에서 설명한 파라미터(`rclcpp::Parameter`, `rclcpp::ParameterEventHandler`)와 직접적으로 관련이 있습니다.**  

ROS2에서는 파라미터를 **런타임에 변경할 수도 있지만, 실행할 때 미리 설정할 수도 있습니다.**  
- **Launch 파일** (`.launch.py`) → 여러 노드를 실행하면서 파라미터를 설정  
- **YAML 파일** (`.yaml`) → 파라미터를 구조적으로 저장하고, 여러 실행에서 동일한 설정을 유지  

---

# **📌 1️⃣ Launch 파일에서 파라미터 설정 (`.launch.py`)**
**Launch 파일을 사용하면, 노드를 실행할 때 파라미터를 직접 설정할 수 있습니다.**  
💡 **예제:** `launch` 파일에서 `robot_name`과 `max_speed` 파라미터를 설정  

---

### **🔹 1. `launch` 파일 (`my_launch.py`)**
```python
from launch import LaunchDescription
from launch_ros.actions import Node

def generate_launch_description():
    return LaunchDescription([
        Node(
            package='my_package',
            executable='dynamic_parameter_node',
            name='dynamic_parameter_node',
            parameters=[
                {"robot_name": "LaunchBot"},
                {"max_speed": 15}
            ]
        )
    ])
```
✅ **Launch 파일을 실행하면 `robot_name="LaunchBot"`, `max_speed=15`로 설정됨!**  

---

### **🔹 2. Launch 파일 실행**
```bash
ros2 launch my_package my_launch.py
```
✅ **실행하면, 노드에서 초기 파라미터 값을 설정한 값으로 가져옴**  
```
[INFO] [dynamic_parameter_node]: 초기 로봇 이름: LaunchBot
[INFO] [dynamic_parameter_node]: 초기 최대 속도: 15
```
💡 **즉, `launch` 파일을 사용하면 실행할 때 파라미터를 쉽게 설정 가능!**

---

# **📌 2️⃣ YAML 파일에서 파라미터 설정 (`.yaml`)**
**YAML 파일을 사용하면 파라미터를 한 곳에 정리하여 저장할 수 있습니다.**  
💡 **YAML 파일을 사용하면, 여러 실행에서 같은 설정을 쉽게 적용 가능!**

---

### **🔹 1. YAML 파일 생성 (`params.yaml`)**
```yaml
dynamic_parameter_node:
  ros__parameters:
    robot_name: "YAMLBot"
    max_speed: 20
```
✅ **이 파일을 사용하면 노드가 실행될 때 `robot_name="YAMLBot"`, `max_speed=20`으로 설정됨!**  

---

### **🔹 2. YAML 파일을 `launch` 파일에서 사용**
```python
from launch import LaunchDescription
from launch_ros.actions import Node
import os

def generate_launch_description():
    config_file = os.path.join(
        os.path.expanduser('~'), 'ros2_ws', 'src', 'my_package', 'config', 'params.yaml'
    )

    return LaunchDescription([
        Node(
            package='my_package',
            executable='dynamic_parameter_node',
            name='dynamic_parameter_node',
            parameters=[config_file]  # ✅ YAML 파일 로드
        )
    ])
```
✅ **이제 YAML 파일의 내용을 사용하여 파라미터가 설정됨!**  

---

### **🔹 3. 터미널에서 YAML 파일을 직접 적용**
```bash
ros2 run my_package dynamic_parameter_node --ros-args --params-file ~/ros2_ws/src/my_package/config/params.yaml
```
✅ **YAML 파일을 사용하여 실행하면, 설정된 값이 자동으로 적용됨!**
```
[INFO] [dynamic_parameter_node]: 초기 로봇 이름: YAMLBot
[INFO] [dynamic_parameter_node]: 초기 최대 속도: 20
```

---

# **📌 3️⃣ `launch` 파일 vs `YAML` 파일 vs `ros2 param set` 비교**
| 설정 방법 | 설명 | 사용 시점 |
|-----------|------------------------------|------------|
| **Launch 파일 (`.launch.py`)** | 실행할 때 파라미터 설정 가능 | **노드 실행 시** |
| **YAML 파일 (`.yaml`)** | 파라미터를 파일로 관리하여 재사용 가능 | **노드 실행 시** |
| **`ros2 param set` 명령어** | 노드 실행 후 실시간 변경 가능 | **노드 실행 중** |

✅ **즉, `launch`와 `YAML` 파일을 사용하면 노드 실행 시 미리 설정 가능하고, `ros2 param set`을 사용하면 실행 중에 값을 변경할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>

### **✅ 네, 맞습니다! ROS2에서 파라미터를 설정하는 방법은 크게 3가지입니다.**  
1. **Launch 파일 (`.launch.py`)** - 노드 실행 시 파라미터를 설정  
2. **YAML 파일 (`.yaml`)** - 파라미터를 파일로 저장하여 재사용  
3. **`ros2 param set` 명령어** - 노드 실행 후 실시간으로 변경  

---

## **📌 1️⃣ Launch 파일을 사용한 파라미터 설정**
💡 **Launch 파일에서 직접 파라미터를 정의하여 실행할 때 적용**  
```python
from launch import LaunchDescription
from launch_ros.actions import Node

def generate_launch_description():
    return LaunchDescription([
        Node(
            package='my_package',
            executable='dynamic_parameter_node',
            name='dynamic_parameter_node',
            parameters=[
                {"robot_name": "LaunchBot"},
                {"max_speed": 15}
            ]
        )
    ])
```
✅ **Launch 파일 실행**
```bash
ros2 launch my_package my_launch.py
```
✅ **출력 결과**
```
[INFO] [dynamic_parameter_node]: 초기 로봇 이름: LaunchBot
[INFO] [dynamic_parameter_node]: 초기 최대 속도: 15
```
📌 **Launch 파일은 여러 노드를 한 번에 실행할 때 유용**  

---

## **📌 2️⃣ YAML 파일을 사용한 파라미터 설정**
💡 **파라미터를 YAML 파일에 저장하여 재사용 가능**  
```yaml
dynamic_parameter_node:
  ros__parameters:
    robot_name: "YAMLBot"
    max_speed: 20
```
✅ **Launch 파일에서 YAML 적용**
```python
import os
from launch import LaunchDescription
from launch_ros.actions import Node

def generate_launch_description():
    config_file = os.path.join(
        os.path.expanduser('~'), 'ros2_ws', 'src', 'my_package', 'config', 'params.yaml'
    )

    return LaunchDescription([
        Node(
            package='my_package',
            executable='dynamic_parameter_node',
            name='dynamic_parameter_node',
            parameters=[config_file]
        )
    ])
```
✅ **또는 터미널에서 직접 실행 가능**
```bash
ros2 run my_package dynamic_parameter_node --ros-args --params-file ~/ros2_ws/src/my_package/config/params.yaml
```
✅ **출력 결과**
```
[INFO] [dynamic_parameter_node]: 초기 로봇 이름: YAMLBot
[INFO] [dynamic_parameter_node]: 초기 최대 속도: 20
```
📌 **YAML 파일을 사용하면 파라미터 값을 깔끔하게 정리하고 쉽게 수정 가능**  

---

## **📌 3️⃣ `ros2 param set` 명령어를 사용한 실시간 변경**
💡 **노드 실행 중에 값을 동적으로 변경할 때 사용**  
```bash
ros2 param set /dynamic_parameter_node robot_name "RoboMaster"
ros2 param set /dynamic_parameter_node max_speed 25
```
✅ **변경된 값이 실시간으로 적용됨**
```
[INFO] [dynamic_parameter_node]: 로봇 이름 변경: RoboMaster
[INFO] [dynamic_parameter_node]: 최대 속도 변경: 25
```
📌 **실시간으로 값을 변경할 수 있지만, 노드를 다시 실행하면 초기화됨**  

---

## **📌 3가지 설정 방법 비교**
| 설정 방법 | 적용 시점 | 특징 |
|-----------|----------------|--------------------------------|
| **Launch 파일 (`.launch.py`)** | 노드 실행 시 | 실행할 때마다 새로운 값 설정 가능 |
| **YAML 파일 (`.yaml`)** | 노드 실행 시 | 설정 파일을 저장하고 재사용 가능 |
| **`ros2 param set` 명령어** | 노드 실행 중 | 실시간으로 값 변경 가능 |

✅ **이제 ROS2에서 파라미터를 설정하는 3가지 방법을 확실히 이해했네요!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **12. ROS2 로깅 및 디버깅**
ROS2에서 **로깅(Logging)과 디버깅(Debugging)** 은 시스템 상태를 모니터링하고, 오류를 분석하며, 최적화하는 데 중요한 역할을 합니다.  
이번 강의에서는 **C++ 기반의 ROS2 로깅 기능과 디버깅 도구(`ros2 bag`, `gdb`, `valgrind`)를 구체적인 예제와 함께 설명**합니다.

---

# **📌 1️⃣ ROS2 로깅 (`RCLCPP_INFO`, `RCLCPP_DEBUG`, `RCLCPP_WARN`, `RCLCPP_ERROR`)**
### **✅ ROS2에서 로깅이란?**
로깅(Logging)이란 프로그램이 실행되는 동안 **출력하는 로그 메시지**를 의미합니다.  
- `printf()`나 `std::cout`을 직접 사용하는 것은 비효율적이므로, **ROS2에서는 `RCLCPP_*` 매크로를 사용하여 로그를 남깁니다.**
- 로그는 `INFO`, `DEBUG`, `WARN`, `ERROR`, `FATAL`의 다섯 가지 레벨이 있으며, **필요한 정보만 출력할 수 있도록 조정할 수 있습니다.**  

---

## **🔹 1. ROS2 로깅 예제**
💡 **각 로그 레벨을 출력하는 예제 코드**
```cpp
#include "rclcpp/rclcpp.hpp"

class LoggingExample : public rclcpp::Node {
public:
    LoggingExample() : Node("logging_example") {
        RCLCPP_INFO(this->get_logger(), "이것은 INFO 메시지입니다.");
        RCLCPP_DEBUG(this->get_logger(), "이것은 DEBUG 메시지입니다.");
        RCLCPP_WARN(this->get_logger(), "이것은 WARN 메시지입니다.");
        RCLCPP_ERROR(this->get_logger(), "이것은 ERROR 메시지입니다.");
        RCLCPP_FATAL(this->get_logger(), "이것은 FATAL 메시지입니다.");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<LoggingExample>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **이 코드를 실행하면, 로그 메시지가 출력됩니다.**  
```bash
[INFO] [logging_example]: 이것은 INFO 메시지입니다.
[WARN] [logging_example]: 이것은 WARN 메시지입니다.
[ERROR] [logging_example]: 이것은 ERROR 메시지입니다.
[FATAL] [logging_example]: 이것은 FATAL 메시지입니다.
```
❌ `DEBUG` 메시지는 기본적으로 출력되지 않습니다.

---

## **🔹 2. 로깅 레벨 변경 (`--ros-args --log-level`)**
기본적으로 `INFO` 이상의 로그만 출력되지만, **터미널에서 로깅 레벨을 변경할 수 있습니다.**
```bash
ros2 run my_package logging_example --ros-args --log-level DEBUG
```
✅ **출력 결과 (`DEBUG` 메시지도 출력됨)**
```
[DEBUG] [logging_example]: 이것은 DEBUG 메시지입니다.
```
📌 **즉, 로그 레벨을 조정하면 원하는 수준의 메시지만 출력할 수 있습니다.**  

---

## **🔹 3. 로깅 메시지에 변수 포함하기**
```cpp
int speed = 5;
std::string robot_name = "TurtleBot";
RCLCPP_INFO(this->get_logger(), "로봇: %s, 속도: %d", robot_name.c_str(), speed);
```
✅ **결과**
```
[INFO] [logging_example]: 로봇: TurtleBot, 속도: 5
```

---

# **📌 2️⃣ ros2 bag을 활용한 데이터 기록 및 재생**
### **✅ `ros2 bag` 이란?**
`ros2 bag`은 **ROS2의 토픽 데이터를 기록하고 다시 재생하는 기능**을 제공합니다.
- **로봇이 수집한 데이터를 저장하여 후처리 및 분석 가능**
- **시뮬레이션 없이 실제 데이터를 활용하여 테스트 가능**

---

## **🔹 1. ROS2 토픽 데이터 기록 (`ros2 bag record`)**
💡 **예제: `/chatter` 토픽 데이터를 기록하기**
```bash
ros2 bag record -o my_bag /chatter
```
✅ **my_bag/ 디렉토리에 `chatter` 토픽의 데이터가 저장됨.**  
```bash
my_bag/
 ├── metadata.yaml
 ├── my_bag_0.db3
```

---

## **🔹 2. 기록된 데이터 확인 (`ros2 bag info`)**
```bash
ros2 bag info my_bag
```
✅ **출력**
```
Files: my_bag_0.db3
Topic: /chatter (std_msgs/msg/String) [100 messages]
```

---

## **🔹 3. 기록된 데이터 재생 (`ros2 bag play`)**
```bash
ros2 bag play my_bag
```
✅ **저장된 `chatter` 토픽의 데이터가 다시 퍼블리싱됨!**  
📌 **이제 시뮬레이션 없이 실제 데이터를 테스트 가능**

---

# **📌 3️⃣ C++ 디버깅 (`gdb`, `valgrind`)**
### **✅ `gdb` (GNU Debugger) 사용법**
`gdb`는 **C++ 프로그램의 런타임 오류를 디버깅할 때 사용하는 도구**입니다.

---

## **🔹 1. gdb로 ROS2 노드 실행**
```bash
gdb --args ros2 run my_package my_node
```
✅ **gdb 프롬프트에서 실행**
```gdb
(gdb) run
```
📌 **이제 프로그램이 실행되며, 오류가 발생하면 디버깅 가능**

---

## **🔹 2. 코드 실행 중단 및 디버깅**
- **브레이크포인트 설정**
```gdb
(gdb) break my_node.cpp:20  # 20번째 줄에서 실행 중지
```
- **한 줄씩 실행**
```gdb
(gdb) next
```
- **현재 변수 값 확인**
```gdb
(gdb) print variable_name
```

---

### **✅ `valgrind` (메모리 누수 검사)**
`valgrind`는 **메모리 누수와 비효율적인 메모리 사용을 찾아주는 도구**입니다.

---

## **🔹 1. `valgrind`로 ROS2 노드 실행**
```bash
valgrind --leak-check=full --show-leak-kinds=all ros2 run my_package my_node
```
✅ **출력 예제**
```
==12345== LEAK SUMMARY:
==12345== 100 bytes in 5 blocks definitely lost in loss record 1 of 2
```
📌 **메모리 누수가 발생한 경우, 어느 코드에서 발생했는지 확인 가능**

---

## **📌 4️⃣ 최종 정리**
| 기능 | 명령어 | 설명 |
|------|----------------|------------------------------|
| **ROS2 로깅** | `RCLCPP_INFO()` | 노드의 상태를 출력 |
| **로깅 레벨 변경** | `--ros-args --log-level` | DEBUG, WARN, ERROR 선택 가능 |
| **ros2 bag 기록** | `ros2 bag record -o my_bag /chatter` | `/chatter` 토픽을 저장 |
| **ros2 bag 재생** | `ros2 bag play my_bag` | 기록된 데이터를 다시 퍼블리싱 |
| **GDB 디버깅** | `gdb --args ros2 run my_package my_node` | 런타임 디버깅 수행 |
| **Valgrind 메모리 검사** | `valgrind --leak-check=full ros2 run my_package my_node` | 메모리 누수 감지 |

✅ **이제 ROS2에서 로깅, 데이터 기록 및 디버깅을 효과적으로 수행할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **13. ROS2 파일 I/O 및 데이터 처리**
ROS2에서 파일 입출력(File I/O) 및 데이터 처리는 센서 로그 저장, 설정값 로드, 로봇 경로 데이터 분석 등 다양한 상황에서 필요합니다.  
이번 강의에서는 **C++에서 `std::fstream`을 활용한 파일 입출력, CSV/JSON/YAML 데이터 처리 방법**을 예제와 함께 다룹니다.  

---

# **📌 1️⃣ `std::fstream`을 활용한 파일 입출력**
C++ 표준 라이브러리에서 제공하는 `std::fstream`을 사용하면 **텍스트 파일 및 바이너리 파일을 읽고 쓸 수 있습니다.**

---

### **🔹 1. 텍스트 파일 쓰기 (`std::ofstream`)**
💡 **"data.txt" 파일에 데이터를 저장하는 예제**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ofstream file("data.txt");  // 파일 생성 및 열기
    if (!file) {
        std::cerr << "파일을 열 수 없습니다!" << std::endl;
        return 1;
    }

    file << "ROS2 파일 입출력 예제\n";
    file << "로봇 속도: 5.5 m/s\n";
    
    file.close();
    std::cout << "파일 저장 완료!" << std::endl;
    return 0;
}
```
✅ **실행 후 `data.txt` 내용**
```
ROS2 파일 입출력 예제
로봇 속도: 5.5 m/s
```

---

### **🔹 2. 텍스트 파일 읽기 (`std::ifstream`)**
💡 **파일에서 데이터를 읽어오는 예제**
```cpp
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::ifstream file("data.txt");  // 파일 열기
    if (!file) {
        std::cerr << "파일을 열 수 없습니다!" << std::endl;
        return 1;
    }

    std::string line;
    while (std::getline(file, line)) {
        std::cout << line << std::endl;
    }

    file.close();
    return 0;
}
```
✅ **출력**
```
ROS2 파일 입출력 예제
로봇 속도: 5.5 m/s
```

---

### **🔹 3. 바이너리 파일 입출력 (`std::ios::binary`)**
💡 **이진 데이터 저장 및 로드 예제 (센서 데이터 등)**
```cpp
#include <iostream>
#include <fstream>

int main() {
    double sensor_data = 42.195;
    
    // ✅ 바이너리 파일 저장
    std::ofstream out("sensor_data.bin", std::ios::binary);
    out.write(reinterpret_cast<char*>(&sensor_data), sizeof(sensor_data));
    out.close();
    
    // ✅ 바이너리 파일 읽기
    double loaded_data;
    std::ifstream in("sensor_data.bin", std::ios::binary);
    in.read(reinterpret_cast<char*>(&loaded_data), sizeof(loaded_data));
    in.close();

    std::cout << "불러온 센서 데이터: " << loaded_data << std::endl;
    return 0;
}
```
✅ **출력**
```
불러온 센서 데이터: 42.195
```
📌 **바이너리 파일은 텍스트가 아니라 16진수 값으로 저장됨. 빠르게 읽고 쓸 수 있음!**  

---

# **📌 2️⃣ CSV 파일 처리**
💡 **CSV(Comma-Separated Values) 파일은 데이터 로그 저장에 자주 사용됩니다.**  

---

### **🔹 1. CSV 파일 쓰기**
💡 **로봇의 속도를 저장하는 `speed_log.csv` 파일을 생성**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ofstream file("speed_log.csv");
    file << "Time,Speed\n";
    file << "1,1.5\n";
    file << "2,2.0\n";
    file << "3,2.5\n";
    file.close();
    
    std::cout << "CSV 저장 완료!" << std::endl;
    return 0;
}
```
✅ **파일 내용 (`speed_log.csv`)**
```
Time,Speed
1,1.5
2,2.0
3,2.5
```

---

### **🔹 2. CSV 파일 읽기**
💡 **파일에서 데이터를 읽어 출력하는 예제**
```cpp
#include <iostream>
#include <fstream>
#include <sstream>

int main() {
    std::ifstream file("speed_log.csv");
    std::string line;
    
    while (std::getline(file, line)) {
        std::stringstream ss(line);
        std::string time, speed;
        std::getline(ss, time, ',');
        std::getline(ss, speed, ',');

        std::cout << "시간: " << time << ", 속도: " << speed << std::endl;
    }
    
    return 0;
}
```
✅ **출력**
```
시간: Time, 속도: Speed
시간: 1, 속도: 1.5
시간: 2, 속도: 2.0
시간: 3, 속도: 2.5
```
📌 **첫 번째 행(헤더)을 무시하려면 `std::getline(file, line);`을 추가**  

---

# **📌 3️⃣ JSON 파일 처리 (`nlohmann/json`)**
💡 **C++에서는 `nlohmann/json` 라이브러리를 사용하여 JSON 파일을 쉽게 처리할 수 있습니다.**

---

### **🔹 1. JSON 파일 쓰기**
💡 **로봇의 설정을 `config.json`에 저장**
```cpp
#include <iostream>
#include <fstream>
#include "nlohmann/json.hpp"

using json = nlohmann::json;

int main() {
    json config;
    config["robot_name"] = "TurtleBot";
    config["max_speed"] = 5.0;
    config["sensors"] = {"LiDAR", "Camera"};

    std::ofstream file("config.json");
    file << config.dump(4);  // ✅ JSON을 보기 좋게 저장
    file.close();

    std::cout << "JSON 저장 완료!" << std::endl;
    return 0;
}
```
✅ **파일 내용 (`config.json`)**
```json
{
    "robot_name": "TurtleBot",
    "max_speed": 5.0,
    "sensors": ["LiDAR", "Camera"]
}
```

---

### **🔹 2. JSON 파일 읽기**
```cpp
std::ifstream file("config.json");
json config;
file >> config;
file.close();

std::cout << "로봇 이름: " << config["robot_name"] << std::endl;
std::cout << "최대 속도: " << config["max_speed"] << std::endl;
```
✅ **출력**
```
로봇 이름: TurtleBot
최대 속도: 5
```

---

# **📌 4️⃣ YAML 파일 처리 (`yaml-cpp`)**
💡 **YAML은 ROS2에서 설정 파일로 자주 사용됩니다.**

---

### **🔹 1. YAML 파일 쓰기 (`config.yaml`)**
```cpp
#include <iostream>
#include <fstream>
#include "yaml-cpp/yaml.h"

int main() {
    YAML::Node config;
    config["robot_name"] = "TurtleBot";
    config["max_speed"] = 5.0;
    
    std::ofstream file("config.yaml");
    file << config;
    file.close();

    std::cout << "YAML 저장 완료!" << std::endl;
    return 0;
}
```
✅ **파일 내용 (`config.yaml`)**
```yaml
robot_name: TurtleBot
max_speed: 5.0
```

---

### **🔹 2. YAML 파일 읽기**
```cpp
YAML::Node config = YAML::LoadFile("config.yaml");
std::cout << "로봇 이름: " << config["robot_name"].as<std::string>() << std::endl;
std::cout << "최대 속도: " << config["max_speed"].as<double>() << std::endl;
```
✅ **출력**
```
로봇 이름: TurtleBot
최대 속도: 5.0
```

---

# **📌 최종 정리**
| 포맷 | 읽기/쓰기 방식 | 라이브러리 |
|------|--------------|------------|
| **TXT** | `std::fstream` | C++ 기본 |
| **CSV** | `std::fstream` + `std::stringstream` | C++ 기본 |
| **JSON** | `nlohmann/json` | `nlohmann/json.hpp` |
| **YAML** | `yaml-cpp` | `yaml-cpp` |

✅ **이제 ROS2에서 다양한 파일 형식을 C++로 다룰 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **14. ROS2 플러그인과 C++ 인터페이스**
ROS2에서는 **플러그인(`pluginlib`)과 C++ 인터페이스(`rclcpp::NodeInterfaces`)** 를 활용하여 **모듈화된 기능을 동적으로 로드하고, 노드의 다양한 기능을 인터페이스로 관리**할 수 있습니다.  
이번 강의에서는 **ROS2 플러그인 시스템과 C++ 인터페이스를 활용하는 방법을 예제와 함께 설명**합니다.

---

# **📌 1️⃣ ROS2 플러그인 시스템 (`pluginlib`)**
## **✅ `pluginlib`란?**
- **ROS2의 `pluginlib`는 특정 기능을 독립적인 플러그인으로 구현하고, 런타임에 동적으로 로드하는 기능**을 제공합니다.
- 즉, **소스 코드를 수정하지 않고도 새로운 기능을 추가하거나 교체할 수 있도록 설계**할 수 있습니다.
- 플러그인은 주로 **로봇 제어 알고리즘, 센서 드라이버, 플래너 등의 모듈화된 기능**을 만들 때 사용됩니다.

---

## **📌 2️⃣ `pluginlib`를 활용한 ROS2 플러그인 개발**
💡 **예제: 다양한 이동 전략(Strategy)을 플러그인으로 구현하여 런타임에 로드하기**

---

### **🔹 1. 플러그인 인터페이스 정의**
먼저, 플러그인이 공통으로 구현해야 하는 **인터페이스 클래스**를 정의합니다.

📌 **`include/my_plugin_base/movement_strategy.hpp`**
```cpp
#ifndef MOVEMENT_STRATEGY_HPP
#define MOVEMENT_STRATEGY_HPP

#include <string>

class MovementStrategy {
public:
    virtual ~MovementStrategy() = default;
    virtual std::string move() = 0;
};

#endif // MOVEMENT_STRATEGY_HPP
```
✅ **모든 이동 전략(플러그인)은 `MovementStrategy` 클래스를 상속받아야 함**  
✅ **`move()` 함수는 각 플러그인에서 다르게 구현됨**

---

### **🔹 2. 플러그인 구현 (예: 직선 이동)**
📌 **`src/straight_movement.cpp`**
```cpp
#include "my_plugin_base/movement_strategy.hpp"
#include <pluginlib/class_list_macros.hpp>

class StraightMovement : public MovementStrategy {
public:
    std::string move() override {
        return "로봇이 직선으로 이동합니다.";
    }
};

// ✅ 이 클래스를 플러그인으로 등록
PLUGINLIB_EXPORT_CLASS(StraightMovement, MovementStrategy)
```
✅ **`StraightMovement`는 `MovementStrategy` 인터페이스를 구현한 플러그인 클래스**  
✅ **`PLUGINLIB_EXPORT_CLASS()` 매크로를 사용하여 플러그인으로 등록**

---

### **🔹 3. 플러그인 구현 (예: 곡선 이동)**
📌 **`src/curved_movement.cpp`**
```cpp
#include "my_plugin_base/movement_strategy.hpp"
#include <pluginlib/class_list_macros.hpp>

class CurvedMovement : public MovementStrategy {
public:
    std::string move() override {
        return "로봇이 곡선으로 이동합니다.";
    }
};

// ✅ 곡선 이동 전략을 플러그인으로 등록
PLUGINLIB_EXPORT_CLASS(CurvedMovement, MovementStrategy)
```
✅ **여러 개의 이동 전략을 각각 플러그인으로 등록 가능**

---

### **🔹 4. 플러그인 호출 및 실행**
📌 **`src/plugin_loader.cpp`**
```cpp
#include <iostream>
#include <pluginlib/class_loader.hpp>
#include "my_plugin_base/movement_strategy.hpp"

int main() {
    try {
        // ✅ 플러그인 로더 생성
        pluginlib::ClassLoader<MovementStrategy> loader("my_plugin_package", "MovementStrategy");

        // ✅ "StraightMovement" 플러그인 로드
        auto straight_movement = loader.createSharedInstance("StraightMovement");
        std::cout << straight_movement->move() << std::endl;

        // ✅ "CurvedMovement" 플러그인 로드
        auto curved_movement = loader.createSharedInstance("CurvedMovement");
        std::cout << curved_movement->move() << std::endl;

    } catch (const pluginlib::PluginlibException &ex) {
        std::cerr << "플러그인 로드 실패: " << ex.what() << std::endl;
    }
    return 0;
}
```
✅ **런타임에 `StraightMovement`와 `CurvedMovement` 플러그인을 동적으로 로드**  
✅ **소스 코드 수정 없이 새로운 플러그인을 추가할 수 있음!**  

---

### **🔹 5. 실행 결과**
```bash
로봇이 직선으로 이동합니다.
로봇이 곡선으로 이동합니다.
```
📌 **즉, `pluginlib`를 사용하면 새로운 기능을 쉽게 추가하고, 코드 수정 없이 확장 가능** 🚀

---

# **📌 3️⃣ ROS2 C++ 인터페이스 (`rclcpp::NodeInterfaces`)**
## **✅ `rclcpp::NodeInterfaces`란?**
ROS2에서는 **각 노드가 여러 인터페이스를 가질 수 있도록 `rclcpp::NodeInterfaces`를 제공**합니다.  
이를 활용하면 **노드의 구성 요소를 더 모듈화하여 관리할 수 있습니다.**

---

## **📌 4️⃣ `rclcpp::NodeInterfaces` 활용 예제**
💡 **각각의 인터페이스(`rclcpp::NodeLogging`, `rclcpp::NodeClock`)를 직접 가져와서 사용**

---

### **🔹 1. 기본 노드 구현**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "노드가 시작되었습니다.");
    }
};
```
✅ **일반적인 ROS2 노드의 로깅 기능(`get_logger()`)은 내부적으로 `rclcpp::NodeLogging`을 사용**

---

### **🔹 2. `rclcpp::NodeInterfaces`를 활용한 노드**
📌 **인터페이스를 직접 접근하여 활용**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNodeWithInterfaces : public rclcpp::Node {
public:
    MyNodeWithInterfaces() : Node("my_node_with_interfaces") {
        auto logging = this->get_node_logging_interface();
        auto clock = this->get_node_clock_interface();

        RCLCPP_INFO(logging->get_logger(), "이 노드는 인터페이스 기반으로 동작합니다.");
        RCLCPP_INFO(logging->get_logger(), "현재 시간: %ld", clock->get_clock()->now().nanoseconds());
    }
};
```
✅ **`get_node_logging_interface()`를 사용하여 로깅 기능을 직접 가져와 활용**  
✅ **`get_node_clock_interface()`를 사용하여 현재 ROS2 시간 가져오기 가능**

---

### **🔹 3. 실행 결과**
```bash
[INFO] [my_node_with_interfaces]: 이 노드는 인터페이스 기반으로 동작합니다.
[INFO] [my_node_with_interfaces]: 현재 시간: 1643812345123456789
```
📌 **이 방식은 노드의 특정 기능을 독립적으로 분리하여 재사용하기 쉽게 만듦** 🚀

---

# **📌 최종 정리**
| 기능 | 설명 | 주요 클래스 |
|------|------------------|------------------|
| **ROS2 플러그인 (`pluginlib`)** | 런타임에 동적으로 모듈 로드 | `pluginlib::ClassLoader` |
| **ROS2 C++ 인터페이스** | 노드의 구성 요소를 인터페이스로 관리 | `rclcpp::NodeInterfaces` |
| **로깅 인터페이스** | 노드의 로깅 기능 | `rclcpp::NodeLogging` |
| **시간 인터페이스** | ROS2 시간 정보 제공 | `rclcpp::NodeClock` |

✅ **이제 ROS2에서 플러그인(`pluginlib`)을 활용하여 확장 가능한 구조를 만들고, C++ 인터페이스(`rclcpp::NodeInterfaces`)를 사용하여 모듈화된 노드를 개발할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊



<br>
<br>
<br>
<br>
<br>

# **15. ROS2 네비게이션과 SLAM C++ 적용**
ROS2에서는 **Navigation2 (Nav2) 패키지와 SLAM (Simultaneous Localization and Mapping) 패키지**를 활용하여 **자율 주행 로봇의 경로 계획과 맵 생성**을 수행할 수 있습니다.  
이번 강의에서는 **C++을 활용하여 Navigation2 및 SLAM Toolbox, Cartographer SLAM을 제어하는 방법과, ROS2에서 C++ 기반으로 경로 계획을 구현하는 방법**을 설명합니다.

---

# **📌 1️⃣ ROS2 Navigation2 개요 (`nav2_bringup`, `nav2_lifecycle_manager`)**
## **✅ Navigation2란?**
- **ROS2 Navigation2 (Nav2)** 는 자율 주행 로봇의 이동을 위한 패키지로, 경로 생성과 주행을 담당합니다.
- `nav2_bringup` 패키지를 사용하여 **Navigation2를 실행**할 수 있습니다.
- `nav2_lifecycle_manager`를 활용하면 **각 네비게이션 모듈을 시작/중지/제어할 수 있습니다.**

---

## **📌 2️⃣ C++ 코드로 Navigation2 제어**
💡 **C++을 사용하여 Navigation2를 실행하고, 상태를 제어하는 방법을 설명합니다.**

---

### **🔹 1. Navigation2 실행 (`nav2_bringup`)**
💡 **TurtleBot3에서 Navigation2 실행 예제**
```bash
export TURTLEBOT3_MODEL=waffle
ros2 launch nav2_bringup tb3_simulation_launch.py
```
✅ **이 명령어를 실행하면 TurtleBot3가 Gazebo에서 Navigation2를 실행하며 주행 가능**  

---

### **🔹 2. C++ 코드로 Navigation2 상태 관리 (`nav2_lifecycle_manager`)**
💡 **C++에서 Navigation2의 생명주기(lifecycle) 상태를 제어하기**
📌 **코드: Navigation2 Lifecycle 활성화**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "nav2_msgs/srv/manage_lifecycle_nodes.hpp"

class Nav2Manager : public rclcpp::Node {
public:
    Nav2Manager() : Node("nav2_manager") {
        client_ = this->create_client<nav2_msgs::srv::ManageLifecycleNodes>("/lifecycle_manager_navigation/manage_nodes");

        while (!client_->wait_for_service(std::chrono::seconds(2))) {
            RCLCPP_WARN(this->get_logger(), "Navigation2 서비스 대기 중...");
        }
        activate_navigation();
    }

private:
    void activate_navigation() {
        auto request = std::make_shared<nav2_msgs::srv::ManageLifecycleNodes::Request>();
        request->command = nav2_msgs::srv::ManageLifecycleNodes::Request::ACTIVATE;

        auto result = client_->async_send_request(request);
        RCLCPP_INFO(this->get_logger(), "Navigation2 활성화 요청 전송...");
    }

    rclcpp::Client<nav2_msgs::srv::ManageLifecycleNodes>::SharedPtr client_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<Nav2Manager>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **`nav2_lifecycle_manager`를 사용하여 Navigation2를 활성화하고, 로봇을 주행할 수 있도록 설정 가능**  
✅ **이제 Navigation2가 활성화되었으므로 경로를 설정할 수 있음!**  

---

# **📌 3️⃣ SLAM Toolbox 및 Cartographer SLAM을 C++ 코드로 제어**
## **✅ SLAM Toolbox와 Cartographer란?**
- **SLAM Toolbox**: ROS2에서 사용되는 경량 SLAM 패키지 (2D SLAM에 적합)
- **Cartographer**: Google에서 개발한 SLAM 알고리즘 (고품질의 2D/3D SLAM 지원)

---

### **🔹 1. SLAM Toolbox 실행**
💡 **TurtleBot3에서 SLAM Toolbox 실행**
```bash
export TURTLEBOT3_MODEL=waffle
ros2 launch slam_toolbox online_async_launch.py
```
✅ **이제 `/map` 토픽에서 생성된 맵을 수신할 수 있음**  

---

### **🔹 2. C++ 코드로 맵 저장 요청 (`map_saver_cli`)**
💡 **SLAM이 완료된 후 맵을 저장하는 C++ 코드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "nav_msgs/srv/save_map.hpp"

class SaveMapClient : public rclcpp::Node {
public:
    SaveMapClient() : Node("save_map_client") {
        client_ = this->create_client<nav_msgs::srv::SaveMap>("/map_saver/save_map");

        while (!client_->wait_for_service(std::chrono::seconds(2))) {
            RCLCPP_WARN(this->get_logger(), "맵 저장 서비스 대기 중...");
        }
        save_map();
    }

private:
    void save_map() {
        auto request = std::make_shared<nav_msgs::srv::SaveMap::Request>();
        request->map_url = "my_map";
        request->map_mode = "trinary";
        
        auto result = client_->async_send_request(request);
        RCLCPP_INFO(this->get_logger(), "맵 저장 요청 전송...");
    }

    rclcpp::Client<nav_msgs::srv::SaveMap>::SharedPtr client_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<SaveMapClient>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **이제 `my_map.pgm`과 `my_map.yaml` 파일이 저장됨!**  

---

# **📌 4️⃣ ROS2에서 C++로 경로 계획 (`nav_msgs::Path`)**
## **✅ `nav_msgs::Path`란?**
- 로봇이 목표 지점까지 이동하는 경로를 **경로 계획(Path Planning)** 을 통해 생성함.
- `nav_msgs::Path` 메시지는 로봇의 경로를 표현하는 표준 메시지 타입.

---

### **🔹 1. 경로 생성 및 퍼블리싱**
💡 **C++에서 목표 경로(`nav_msgs::Path`)를 생성하여 퍼블리싱하는 코드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "nav_msgs/msg/path.hpp"
#include "geometry_msgs/msg/pose_stamped.hpp"

class PathPublisher : public rclcpp::Node {
public:
    PathPublisher() : Node("path_publisher") {
        publisher_ = this->create_publisher<nav_msgs::msg::Path>("/planned_path", 10);
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&PathPublisher::publishPath, this));
    }

private:
    void publishPath() {
        nav_msgs::msg::Path path;
        path.header.stamp = this->get_clock()->now();
        path.header.frame_id = "map";

        for (int i = 0; i < 5; i++) {
            geometry_msgs::msg::PoseStamped pose;
            pose.header = path.header;
            pose.pose.position.x = i;
            pose.pose.position.y = i * 0.5;
            pose.pose.position.z = 0.0;
            pose.pose.orientation.w = 1.0;
            path.poses.push_back(pose);
        }

        publisher_->publish(path);
        RCLCPP_INFO(this->get_logger(), "경로 퍼블리싱 완료!");
    }

    rclcpp::Publisher<nav_msgs::msg::Path>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<PathPublisher>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **경로 계획 데이터를 `/planned_path` 토픽으로 퍼블리싱**  
✅ **Rviz2에서 `/planned_path` 토픽을 시각화 가능!**  

---

# **📌 최종 정리**
| 기능 | 사용 패키지 | 설명 |
|------|-----------|------------------------------|
| **Navigation2 활성화** | `nav2_lifecycle_manager` | 네비게이션 모듈 제어 |
| **SLAM 실행** | `slam_toolbox`, `cartographer` | 맵 생성 및 저장 |
| **맵 저장** | `map_saver_cli` | 생성된 맵을 `.pgm`, `.yaml`로 저장 |
| **경로 계획** | `nav_msgs::Path` | 목표 경로 생성 및 퍼블리싱 |

✅ **이제 ROS2에서 C++을 활용하여 Navigation2, SLAM, 경로 계획을 구현할 수 있습니다!** 🚀  


<br>
<br>
<br>
<br>
<br>

# **16. ROS2에서 C++로 AI 및 컴퓨터 비전 적용**
ROS2에서 **AI 및 컴퓨터 비전을 C++로 적용하는 방법**을 다루며,  
- **OpenCV (`cv_bridge`)를 활용한 이미지 처리**  
- **YOLO 및 ONNX Runtime을 활용한 딥러닝 모델 실행**  
- **ROS2에서 `rclcpp::Subscription<ImageMsg>`을 활용한 실시간 이미지 스트리밍 처리**  

등을 자세히 설명합니다.

---

# **📌 1️⃣ OpenCV를 활용한 이미지 처리 (`cv_bridge`)**
## **✅ `cv_bridge`란?**
- ROS2의 이미지 메시지 (`sensor_msgs::msg::Image`)를 OpenCV의 `cv::Mat` 형식으로 변환할 수 있도록 도와줌
- 이를 활용하면 ROS2에서 **카메라 데이터 처리, 이미지 변환, 객체 감지** 등의 작업을 쉽게 수행 가능

---

### **🔹 1. ROS2에서 OpenCV와 `cv_bridge` 설치**
```bash
sudo apt install ros-humble-vision-opencv
sudo apt install ros-humble-cv-bridge
```
✅ **설치 후 `CMakeLists.txt`에서 OpenCV와 `cv_bridge` 추가**  
📌 **`CMakeLists.txt` 설정**
```cmake
find_package(OpenCV REQUIRED)
find_package(cv_bridge REQUIRED)

target_link_libraries(${PROJECT_NAME}
  ${OpenCV_LIBS}
  cv_bridge::cv_bridge
)
```

---

## **🔹 2. ROS2에서 카메라 영상을 받아 OpenCV로 처리**
💡 **ROS2 카메라 노드에서 이미지를 구독하고 OpenCV로 변환하여 표시하는 코드**
📌 **`image_processor.cpp`**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "sensor_msgs/msg/image.hpp"
#include "cv_bridge/cv_bridge.h"
#include "opencv2/opencv.hpp"

class ImageProcessor : public rclcpp::Node {
public:
    ImageProcessor() : Node("image_processor") {
        subscription_ = this->create_subscription<sensor_msgs::msg::Image>(
            "/camera/image_raw", 10,
            std::bind(&ImageProcessor::imageCallback, this, std::placeholders::_1));
    }

private:
    void imageCallback(const sensor_msgs::msg::Image::SharedPtr msg) {
        try {
            cv::Mat img = cv_bridge::toCvCopy(msg, "bgr8")->image;
            cv::imshow("Camera Feed", img);
            cv::waitKey(1);
        } catch (cv_bridge::Exception &e) {
            RCLCPP_ERROR(this->get_logger(), "cv_bridge 변환 실패: %s", e.what());
        }
    }

    rclcpp::Subscription<sensor_msgs::msg::Image>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<ImageProcessor>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **실시간으로 `/camera/image_raw` 토픽의 이미지를 OpenCV로 변환하여 화면에 표시**  
✅ **`cv_bridge::toCvCopy()`를 사용하여 `sensor_msgs::msg::Image` → `cv::Mat` 변환**  
✅ **카메라가 없을 경우 `ros2 run image_tools cam2image` 실행하여 테스트 가능**  

---

# **📌 2️⃣ YOLO 및 ONNX Runtime을 활용한 딥러닝 모델 실행**
## **✅ ONNX Runtime이란?**
- 다양한 **딥러닝 프레임워크(TensorFlow, PyTorch 등)에서 학습한 모델을 실행**할 수 있도록 하는 **고성능 추론 엔진**
- ROS2 C++에서 **YOLO, ResNet 등의 모델을 실행 가능**  
- **GPU 가속(CUDA, TensorRT) 지원**

---

## **🔹 1. ONNX Runtime 설치**
```bash
sudo apt install ros-humble-onnx-runtime
```

---

## **🔹 2. YOLO 모델을 ONNX 형식으로 변환**
💡 **YOLOv8을 사용하여 `yolov8.onnx` 모델을 다운로드**
```python
from ultralytics import YOLO
model = YOLO("yolov8n.pt")
model.export(format="onnx")
```
✅ **이제 `yolov8n.onnx` 파일이 생성됨. ROS2 C++에서 실행 가능!**  

---

## **🔹 3. ROS2 C++에서 YOLO 모델 로드 및 실행**
📌 **`yolo_detector.cpp`**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "sensor_msgs/msg/image.hpp"
#include "cv_bridge/cv_bridge.h"
#include "opencv2/opencv.hpp"
#include "onnxruntime/core/session/onnxruntime_cxx_api.h"

class YoloDetector : public rclcpp::Node {
public:
    YoloDetector() : Node("yolo_detector") {
        session_ = std::make_unique<Ort::Session>(env_, "yolov8n.onnx", Ort::SessionOptions{});
        subscription_ = this->create_subscription<sensor_msgs::msg::Image>(
            "/camera/image_raw", 10,
            std::bind(&YoloDetector::imageCallback, this, std::placeholders::_1));
    }

private:
    void imageCallback(const sensor_msgs::msg::Image::SharedPtr msg) {
        cv::Mat img = cv_bridge::toCvCopy(msg, "bgr8")->image;

        // ✅ ONNX 모델을 사용하여 YOLO 추론 수행 (예제 코드)
        // 실제 ONNX 모델 실행은 `session_->Run(...)`을 통해 진행됨

        RCLCPP_INFO(this->get_logger(), "YOLO 객체 탐지 완료!");
        cv::imshow("YOLO Detection", img);
        cv::waitKey(1);
    }

    Ort::Env env_{ORT_LOGGING_LEVEL_WARNING, "YOLOv8"};
    std::unique_ptr<Ort::Session> session_;
    rclcpp::Subscription<sensor_msgs::msg::Image>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<YoloDetector>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **YOLOv8 ONNX 모델을 불러와 ROS2 카메라 이미지에서 객체를 탐지**  
✅ **실제 추론 결과를 사용하려면 `session_->Run()`을 사용하여 바운딩 박스를 그려야 함**  

---

# **📌 3️⃣ ROS2에서 `rclcpp::Subscription<ImageMsg>`을 활용한 이미지 스트림 처리**
## **✅ 이미지 스트림이란?**
- **카메라 센서 또는 이미지 데이터 스트림을 실시간으로 처리**하는 기능  
- ROS2에서는 `sensor_msgs::msg::Image` 형식의 메시지를 이용하여 이미지를 주고받음  
- **YOLO, OpenCV 필터 적용, 이미지 저장, 로깅 등에 활용 가능**

---

### **🔹 1. 이미지 저장 노드 구현**
📌 **`image_saver.cpp`**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "sensor_msgs/msg/image.hpp"
#include "cv_bridge/cv_bridge.h"
#include "opencv2/opencv.hpp"

class ImageSaver : public rclcpp::Node {
public:
    ImageSaver() : Node("image_saver") {
        subscription_ = this->create_subscription<sensor_msgs::msg::Image>(
            "/camera/image_raw", 10,
            std::bind(&ImageSaver::imageCallback, this, std::placeholders::_1));
    }

private:
    void imageCallback(const sensor_msgs::msg::Image::SharedPtr msg) {
        cv::Mat img = cv_bridge::toCvCopy(msg, "bgr8")->image;
        std::string filename = "saved_image.jpg";
        cv::imwrite(filename, img);
        RCLCPP_INFO(this->get_logger(), "이미지 저장 완료: %s", filename.c_str());
    }

    rclcpp::Subscription<sensor_msgs::msg::Image>::SharedPtr subscription_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<ImageSaver>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **실시간 이미지 스트림을 구독하고 자동으로 저장**  
✅ **이제 ROS2 카메라 데이터를 쉽게 저장하고 분석할 수 있음**  

---

# **📌 최종 정리**
| 기능 | 설명 | 주요 클래스 |
|------|----------------------|----------------------|
| **OpenCV 처리** | `cv_bridge`로 ROS 이미지 변환 | `cv_bridge::toCvCopy()` |
| **YOLO 딥러닝 적용** | ONNX Runtime으로 YOLO 실행 | `Ort::Session` |
| **이미지 스트리밍** | 실시간 이미지 처리 | `rclcpp::Subscription<ImageMsg>` |

✅ **이제 ROS2에서 C++을 활용하여 AI 및 컴퓨터 비전을 적용할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>
<br>
<br>

# **17. ROS2 최적화 및 배포**
ROS2에서 **성능 최적화, 크로스 컴파일, Docker를 활용한 배포**는 경량화 및 배포 자동화를 위한 핵심 기술입니다.  
이 강의에서는 **C++ 기반 ROS2 애플리케이션의 성능을 최적화하고, 크로스 컴파일 및 Docker를 활용하여 배포하는 방법을 설명**합니다.

---

# **📌 1️⃣ 성능 최적화 (`rclcpp::Timer` 활용)**
## **✅ `rclcpp::Timer`란?**
- ROS2에서는 **CPU 사용량을 줄이고, 효율적인 주기적 실행을 위해 `rclcpp::Timer`를 활용**합니다.
- **`spin()`을 계속 실행하는 방식보다 `Timer`를 사용하면 더 가벼운 구조**를 만들 수 있습니다.

---

## **🔹 1. `spin()`과 `rclcpp::Timer` 비교**
💡 **일반적인 `spin()` 사용 예제**
```cpp
#include "rclcpp/rclcpp.hpp"

class HighLoadNode : public rclcpp::Node {
public:
    HighLoadNode() : Node("high_load_node") {
        while (rclcpp::ok()) {
            RCLCPP_INFO(this->get_logger(), "CPU 부하 발생!");
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<HighLoadNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **CPU를 과도하게 사용하여 부하가 높아지는 문제 발생**  

---

💡 **`rclcpp::Timer`를 활용하여 CPU 사용량을 줄이는 최적화 예제**
```cpp
#include "rclcpp/rclcpp.hpp"

class OptimizedNode : public rclcpp::Node {
public:
    OptimizedNode() : Node("optimized_node") {
        timer_ = this->create_wall_timer(std::chrono::seconds(1),
            std::bind(&OptimizedNode::timerCallback, this));
    }

private:
    void timerCallback() {
        RCLCPP_INFO(this->get_logger(), "1초마다 실행 중...");
    }

    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<OptimizedNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
✅ **CPU 사용량을 줄이고 주기적으로 실행하는 구조로 최적화됨!**  
✅ **ROS2에서 주기적인 작업을 실행할 때 `while` 대신 `rclcpp::Timer`를 적극 활용할 것!**  

---

# **📌 2️⃣ 크로스 컴파일 및 경량화 (`ros2 cross_compile`)**
## **✅ 크로스 컴파일이란?**
- **크로스 컴파일(Cross Compilation)** 은 **개발 환경과 실행 환경이 다른 경우** 사용할 수 있는 기술입니다.
- **x86_64 (데스크탑) → ARM (라즈베리파이, NVIDIA Jetson 등) 환경으로 빌드 가능**
- `ros2 cross_compile`을 사용하면 **개발 PC에서 타겟 아키텍처용 실행 파일을 미리 빌드 가능**  

---

## **🔹 1. `ros2 cross_compile` 설치**
```bash
pip install -U colcon-common-extensions ros_cross_compile
```

---

## **🔹 2. 크로스 컴파일 실행**
💡 **라즈베리파이(ARM64)용 ROS2 패키지 크로스 컴파일**
```bash
ros2 run ros_cross_compile cross_compile --arch aarch64 --os ubuntu --rosdistro humble --workspace ~/ros2_ws
```
✅ **x86 환경에서 ARM64용 실행 파일을 빌드 가능**  
✅ **라즈베리파이, Jetson 등 임베디드 환경에서 ROS2 실행 가능!**

---

# **📌 3️⃣ Docker를 활용한 ROS2 배포**
## **✅ Docker란?**
- **Docker를 활용하면 ROS2 환경을 컨테이너화하여 손쉽게 배포 가능**
- **개발 환경과 배포 환경을 일치시켜 문제를 최소화할 수 있음**

---

## **🔹 1. Dockerfile을 사용한 ROS2 컨테이너 생성**
📌 **`Dockerfile`**
```dockerfile
# ✅ 1. ROS2 Humble 이미지 기반
FROM osrf/ros:humble-desktop

# ✅ 2. 작업 디렉토리 설정
WORKDIR /ros2_ws

# ✅ 3. ROS2 패키지 복사 및 빌드
COPY . /ros2_ws
RUN apt update && rosdep install --from-paths src --ignore-src -r -y
RUN colcon build

# ✅ 4. 환경 변수 설정
SHELL ["/bin/bash", "-c"]
RUN echo "source /ros2_ws/install/setup.bash" >> ~/.bashrc

# ✅ 5. 기본 실행 명령어
CMD ["bash"]
```

✅ **Docker로 ROS2 개발 환경을 일관되게 유지 가능**  
✅ **다른 개발자가 동일한 환경에서 실행 가능!**

---

## **🔹 2. Docker 컨테이너 빌드 및 실행**
💡 **Docker 이미지 빌드**
```bash
docker build -t my_ros2_image .
```
💡 **Docker 컨테이너 실행**
```bash
docker run -it --rm --net=host my_ros2_image
```
✅ **Docker에서 ROS2 실행 가능!**

---

## **🔹 3. `ros_entrypoint.sh`를 활용한 자동 실행**
📌 **`ros_entrypoint.sh`**
```bash
#!/bin/bash
set -e
source /opt/ros/humble/setup.bash
exec "$@"
```
📌 **Dockerfile에서 적용**
```dockerfile
COPY ros_entrypoint.sh /ros_entrypoint.sh
ENTRYPOINT ["/ros_entrypoint.sh"]
```
✅ **컨테이너 실행 시 자동으로 ROS2 환경이 설정됨**  

---

# **📌 최종 정리**
| 최적화/배포 방식 | 설명 | 주요 기술 |
|------|------------------|------------------|
| **CPU 최적화** | `rclcpp::Timer`를 사용하여 CPU 부하 줄이기 | `rclcpp::Timer` |
| **크로스 컴파일** | x86 환경에서 ARM64용 ROS2 빌드 | `ros2 cross_compile` |
| **Docker 배포** | 컨테이너로 ROS2 환경 제공 | `Dockerfile`, `ros_entrypoint.sh` |

✅ **이제 ROS2 애플리케이션을 최적화하고, 크로스 컴파일 및 Docker로 배포할 수 있습니다!** 🚀  
추가 질문이 있으면 언제든지 물어보세요! 😊


<br>
<br>
<br>

# **📌 ROS2 Docker 활용 및 배포 예제**
Docker를 활용하면 **ROS2 개발 환경을 컨테이너로 패키징하여 손쉽게 배포 및 실행**할 수 있습니다.  
이 강의에서는 **다양한 Docker 예제를 통해 ROS2 컨테이너를 구축, 실행, 네트워크 설정, 다중 컨테이너 구성** 등을 다룹니다.

---

# **📌 1️⃣ Docker 기본 개념 및 설치**
## **✅ Docker란?**
- **컨테이너(Container) 기반 가상화 기술**  
- **호스트 OS와 독립적으로 실행되는 가벼운 실행 환경 제공**  
- **ROS2 개발 및 배포 시 동일한 환경을 유지할 수 있음**  

---

## **🔹 1. Docker 설치**
💡 **Ubuntu에서 Docker 설치**
```bash
sudo apt update
sudo apt install -y docker.io
```
✅ **Docker 서비스 실행 및 자동 시작 설정**
```bash
sudo systemctl start docker
sudo systemctl enable docker
```
✅ **사용자를 `docker` 그룹에 추가하여 `sudo` 없이 실행 가능**
```bash
sudo usermod -aG docker $USER
newgrp docker
```

---

# **📌 2️⃣ 기본적인 ROS2 Docker 컨테이너 실행**
## **✅ 1. 공식 ROS2 Docker 이미지 실행**
💡 **기본 ROS2 컨테이너 실행**
```bash
docker run -it --rm osrf/ros:humble bash
```
✅ **이제 ROS2가 실행되는 컨테이너 환경이 제공됨**

---

## **✅ 2. GUI 지원 컨테이너 실행 (RViz2 사용 가능)**
💡 **X11을 활용한 GUI 애플리케이션 실행**
```bash
xhost +
docker run -it --rm --net=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix osrf/ros:humble bash
```
✅ **컨테이너 내에서 `rviz2` 실행 가능**
```bash
rviz2
```
📌 **X11을 활용하면 컨테이너 내 GUI 프로그램을 실행할 수 있음!** 🚀  

---

# **📌 3️⃣ Dockerfile을 사용하여 ROS2 개발 환경 설정**
## **✅ 1. ROS2 Docker 이미지 생성**
💡 **ROS2 워크스페이스를 포함하는 Dockerfile 작성**
📌 **`Dockerfile`**
```dockerfile
# ✅ 1. ROS2 Humble 기본 이미지 사용
FROM osrf/ros:humble

# ✅ 2. ROS2 환경 설정
SHELL ["/bin/bash", "-c"]
RUN echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

# ✅ 3. ROS2 패키지 빌드 준비
WORKDIR /ros2_ws
COPY . /ros2_ws
RUN apt update && rosdep install --from-paths src --ignore-src -r -y
RUN colcon build

# ✅ 4. 컨테이너 실행 시 자동으로 ROS2 환경 로드
CMD ["bash"]
```
✅ **Docker 이미지 빌드**
```bash
docker build -t my_ros2_image .
```
✅ **컨테이너 실행**
```bash
docker run -it --rm my_ros2_image
```
📌 **이제 컨테이너 내에서 ROS2 패키지를 바로 실행 가능!**

---

# **📌 4️⃣ ROS2 노드 실행을 위한 Docker 구성**
## **✅ 1. `ros_entrypoint.sh`를 활용한 자동 실행**
💡 **컨테이너 실행 시 자동으로 ROS2 환경 설정**
📌 **`ros_entrypoint.sh`**
```bash
#!/bin/bash
set -e
source /opt/ros/humble/setup.bash
exec "$@"
```
📌 **Dockerfile에서 엔트리포인트 설정**
```dockerfile
COPY ros_entrypoint.sh /ros_entrypoint.sh
ENTRYPOINT ["/ros_entrypoint.sh"]
```
✅ **이제 컨테이너 실행 시 ROS2 환경이 자동으로 설정됨**  

---

# **📌 5️⃣ 다중 컨테이너를 활용한 ROS2 시스템 구축 (`docker-compose`)**
## **✅ 1. `docker-compose`를 활용한 다중 컨테이너 설정**
💡 **여러 개의 ROS2 컨테이너를 동시에 실행하여 노드 간 통신 테스트**
📌 **`docker-compose.yaml`**
```yaml
version: '3'
services:
  talker:
    image: osrf/ros:humble
    command: ros2 run demo_nodes_cpp talker
    network_mode: "host"

  listener:
    image: osrf/ros:humble
    command: ros2 run demo_nodes_cpp listener
    network_mode: "host"
```
✅ **다중 컨테이너 실행**
```bash
docker-compose up
```
✅ **출력 예제**
```
talker_1  | Publishing: "Hello World"
listener_1 | I heard: "Hello World"
```
📌 **Docker 컨테이너 간 ROS2 통신이 정상적으로 동작!** 🚀  

---

# **📌 6️⃣ Docker 컨테이너에서 ROS2 네트워크 설정**
## **✅ 1. `--net=host` 옵션을 활용한 네트워크 공유**
💡 **다른 호스트 및 컨테이너와 ROS2 노드 간 통신**
```bash
docker run -it --rm --net=host osrf/ros:humble
```
✅ **이제 컨테이너가 호스트 네트워크를 그대로 사용하여 ROS2 메시지 송수신 가능**  

---

## **✅ 2. `bridge` 네트워크 사용**
💡 **컨테이너 간 ROS2 통신을 위해 `bridge` 네트워크 설정**
```bash
docker network create ros2_net
docker run -it --rm --network=ros2_net --name talker osrf/ros:humble ros2 run demo_nodes_cpp talker
docker run -it --rm --network=ros2_net --name listener osrf/ros:humble ros2 run demo_nodes_cpp listener
```
📌 **이제 `talker` 컨테이너와 `listener` 컨테이너가 `ros2_net` 네트워크를 통해 통신 가능!**

---

# **📌 7️⃣ 최적화된 ROS2 Docker 이미지 생성**
## **✅ 1. `multi-stage build`를 활용한 경량화**
💡 **개발 환경과 실행 환경을 분리하여 컨테이너 크기 최소화**
📌 **`Dockerfile`**
```dockerfile
# ✅ 1. 빌드 환경 설정 (Full ROS2 설치)
FROM osrf/ros:humble AS builder
WORKDIR /ros2_ws
COPY . /ros2_ws
RUN apt update && rosdep install --from-paths src --ignore-src -r -y
RUN colcon build

# ✅ 2. 실행 환경 (최소한의 패키지만 포함)
FROM osrf/ros:humble-runtime
WORKDIR /ros2_ws
COPY --from=builder /ros2_ws/install /ros2_ws/install
SHELL ["/bin/bash", "-c"]
RUN echo "source /ros2_ws/install/setup.bash" >> ~/.bashrc

CMD ["bash"]
```
✅ **이제 실행 환경은 경량화되고, 불필요한 빌드 도구가 포함되지 않음**  

---

# **📌 최종 정리**
| 기능 | 설명 | 명령어 / 기술 |
|------|------------------|------------------|
| **기본 컨테이너 실행** | ROS2 기본 컨테이너 실행 | `docker run -it --rm osrf/ros:humble` |
| **GUI 지원 실행** | RViz2 실행 가능 | `xhost + && docker run -e DISPLAY=$DISPLAY` |
| **Dockerfile 활용** | ROS2 개발 환경 설정 | `docker build -t my_ros2 .` |
| **자동 환경 설정** | `ros_entrypoint.sh` 사용 | `ENTRYPOINT ["/ros_entrypoint.sh"]` |
| **다중 컨테이너 실행** | `docker-compose` 활용 | `docker-compose up` |
| **네트워크 설정** | 컨테이너 간 ROS2 통신 | `docker network create ros2_net` |
| **경량화** | `multi-stage build` 활용 | `FROM osrf/ros:humble-runtime` |

✅ **이제 Docker를 활용하여 ROS2를 배포하고 최적화할 수 있습니다!** 🚀  


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
