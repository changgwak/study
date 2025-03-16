# **🔹 `#define`의 역할과 사용 예제**
> **질문:**  
> 1. `#define`은 언제 사용되는가?  
> 2. `#define`을 활용한 다양한 예제와 설명  

---

# **✅ 1) `#define`의 역할**
`#define`은 **C/C++의 전처리기 지시어**로, **코드를 컴파일하기 전에 특정 매크로를 정의**하는 역할을 한다.  
- **매크로 상수**를 정의하여 코드에서 값을 쉽게 변경할 수 있음.
- **함수형 매크로**를 정의하여 **컴파일 타임에 코드 조각을 치환**할 수 있음.
- **조건부 컴파일**을 사용하여 특정 기능을 활성화 또는 비활성화할 수 있음.

---

# **✅ 2) `#define`의 주요 용도**
## **🔹 1) 매크로 상수 정의 (기본적인 `#define` 사용)**
```cpp
#define PI 3.1415926535
#define MAX_SPEED 10.0

double calculate_circle_area(double radius) {
    return PI * radius * radius;
}
```
📌 **이렇게 하면 `PI`를 직접 변경하지 않고 코드 내에서 값만 바꿀 수 있음.**  

---

## **🔹 2) 함수형 매크로 정의**
> **매개변수를 포함하는 `#define`을 이용해 인라인 연산 수행**
```cpp
#define SQUARE(x) ((x) * (x))
#define MAX(a, b) ((a) > (b) ? (a) : (b))

int result1 = SQUARE(5);   // 25
int result2 = MAX(10, 20); // 20
```
📌 **컴파일러가 `SQUARE(5)`를 `((5) * (5))`로 치환하여 실행 속도가 빠름.**  
📌 **단, `inline` 함수가 더 안전하므로 C++에서는 매크로보다 `constexpr`을 권장함.**  

---

## **🔹 3) 조건부 컴파일 (`#ifdef`, `#ifndef`)**
> **특정 기능을 활성화/비활성화하는 데 사용됨**
```cpp
#define DEBUG_MODE  // 주석 처리하면 디버그 비활성화됨

#ifdef DEBUG_MODE
    #define LOG(x) std::cout << "DEBUG: " << x << std::endl;
#else
    #define LOG(x)
#endif

int main() {
    LOG("This is a debug message");  // DEBUG_MODE가 정의되어 있을 때만 출력됨
}
```
📌 **코드 변경 없이 `#define DEBUG_MODE`를 주석 처리하면 디버그 메시지를 비활성화할 수 있음.**  

---

## **🔹 4) 매크로를 이용한 수학 연산 (ROS2 코드에서 사용된 방식)**
> **ROS2 코드에서 `#define`을 활용하여 시간을 계산하는 예제**
```cpp
#define DELTAT(_nowtime, _thentime) ((_thentime > _nowtime) ? ((0xffffffff - _thentime) + _nowtime) : (_nowtime - _thentime))
```
📌 **이 매크로는 두 개의 시간 값을 비교하여 `DELTAT`(시간 차이)를 계산함.**  
📌 **타이머 값이 `0xffffffff`를 넘어갈 때(오버플로우 발생)도 정확한 값을 반환함.**  

---

## **🔹 5) 특정 기능 활성화 (`#define _ODOM_DEBUG`)**
> **ROS2 코드에서 특정 기능을 켜고 끄는 방식**
```cpp
// Define following to enable odom debug output
#define _ODOM_DEBUG

#ifdef _ODOM_DEBUG
    RCLCPP_INFO(this->get_logger(), "Odometry Debug Mode Enabled");
#endif
```
📌 **이렇게 하면 `#define _ODOM_DEBUG`가 설정된 경우에만 디버그 메시지가 출력됨.**  
📌 **디버깅이 필요 없으면 `#define _ODOM_DEBUG`를 주석 처리하면 됨.**  

---

# **✅ 3) `#define` vs `constexpr` vs `const`**
| **기능** | **`#define`** | **`const`** | **`constexpr`** |
|---|---|---|---|
| **컴파일 타임 대체** | ✅ | ❌ | ✅ |
| **메모리 사용** | 없음 (치환) | 변수가 메모리에 존재 | 없음 (컴파일 타임) |
| **디버깅 가능** | ❌ (에러 발생 시 찾기 어려움) | ✅ | ✅ |
| **타입 안전성** | ❌ (타입 없음) | ✅ | ✅ |
| **추천 여부** | ⚠️ (레거시 코드에서만 사용) | ✅ | ✅ |

📌 **C++에서는 `#define` 대신 `constexpr` 또는 `const` 사용을 권장함.**  
📌 **매크로보다 `inline` 함수와 `constexpr`이 더 안전함.**  

---

# **✅ 4) `#define`을 C++에서 사용해야 하는 경우**
✅ **1) 특정 기능을 활성화/비활성화 (`#ifdef`, `#ifndef`)**  
✅ **2) 컴파일 타임에 특정 코드 블록을 제외하고 싶을 때**  
✅ **3) 매우 단순한 매크로 함수 정의 (단, `inline` 함수 사용이 권장됨)**  

📌 **그러나, `#define`의 사용은 최소화하고 `const` 또는 `constexpr`를 선호하는 것이 C++의 모범 사례이다!** 🚀


<br>
<br>
<br>
<br>
<br>
<br>

네! `#define`을 사용한 디버그 모드 활성화 방식 대신 **더 나은 C++ 프로그래밍 방식**이 있습니다.  
**C++에서는 `constexpr`, `const`, `static const`, `enum class`, `std::conditional`, `template`, 그리고 `std::optional` 등을 활용**하여 `#define` 없이 더 안전하고 유지보수하기 좋은 코드를 작성할 수 있습니다.

---

## **✅ 1) `#define` 없이 디버그 모드 활성화하는 더 나은 방법**
### **🔹 방법 1: `constexpr bool` 사용 (C++ 스타일)**
```cpp
constexpr bool ENABLE_ODOM_DEBUG = true;  // ✅ 디버그 모드 ON/OFF 설정

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        if constexpr (ENABLE_ODOM_DEBUG) {  // ✅ 컴파일 타임에 조건이 정해짐
            RCLCPP_INFO(this->get_logger(), "Odometry Debug Mode Enabled");
        }
    }
};
```
✅ **장점**  
- **컴파일 타임에 결정**되므로 `#ifdef`처럼 코드가 완전히 제거됨.
- **타입 안정성 보장** (`bool` 타입이 명확하게 지정됨).
- **IDE에서 검색 가능** (`#define`은 찾기 어려울 수 있음).

---

### **🔹 방법 2: 런타임에서 설정할 수 있도록 `const bool` 사용**
```cpp
const bool enable_odom_debug = true;  // ✅ 런타임에서 설정 가능

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        if (enable_odom_debug) {  // ✅ 런타임에 활성화 가능
            RCLCPP_INFO(this->get_logger(), "Odometry Debug Mode Enabled");
        }
    }
};
```
✅ **장점**  
- 런타임에서 값을 변경할 수 있음.
- `#define`을 제거하고 가독성을 높임.

---

## **✅ 2) 환경 변수 또는 파라미터를 사용하여 `#define` 없이 설정 가능**
**런타임에 디버그 모드를 변경하고 싶다면 ROS2 파라미터를 사용하는 것이 좋다.**

### **🔹 방법 3: ROS2 파라미터 사용 (`rclcpp::Parameter`)**
```cpp
class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        this->declare_parameter("enable_odom_debug", false);  // 기본값 OFF
        bool enable_debug = this->get_parameter("enable_odom_debug").as_bool();

        if (enable_debug) {
            RCLCPP_INFO(this->get_logger(), "Odometry Debug Mode Enabled");
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MyNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
📌 **터미널에서 파라미터 값을 설정하여 디버그 모드 변경 가능!**
```bash
ros2 param set /my_node enable_odom_debug true
```
✅ **장점**  
- 런타임에 동적으로 디버그 모드를 ON/OFF 가능!  
- 코드 재컴파일 없이 설정 변경 가능.  

---

## **✅ 3) C++17 `std::optional`을 활용하여 `#define` 제거**
```cpp
#include <optional>

std::optional<std::string> get_debug_message() {
    return "Odometry Debug Mode Enabled";  // ✅ 필요할 때만 반환
}

if (auto msg = get_debug_message()) {
    RCLCPP_INFO(this->get_logger(), msg.value().c_str());
}
```
✅ **장점**  
- **필요할 때만 값이 존재하므로 `#define` 없이 깔끔하게 구현 가능!**  
- **조건문이 없어도 `std::optional`을 활용하여 불필요한 메시지 생성을 방지.**

---

# **📌 정리**
| 방법 | `#define` 제거 가능 여부 | 런타임 변경 가능 여부 | 장점 |
|---|---|---|---|
| **`constexpr bool` 사용** | ✅ 가능 | ❌ 불가능 (컴파일 타임) | 성능 최적화, 타입 안정성 |
| **`const bool` 사용** | ✅ 가능 | ✅ 가능 (런타임) | 유지보수 쉬움, 코드 가독성 높음 |
| **ROS2 파라미터 사용 (`rclcpp::Parameter`)** | ✅ 가능 | ✅ 가능 (터미널에서 설정 가능) | 재컴파일 없이 설정 변경 가능 |
| **`std::optional` 사용** | ✅ 가능 | ✅ 가능 | 동적 조건 설정, 가독성 향상 |

✅ **최고의 방법은 `constexpr` 또는 `rclcpp::Parameter`를 사용하는 것!** 🚀  
📌 **이제 `#define` 없이 C++ 스타일로 더 깔끔한 ROS2 코드를 작성할 수 있다!** 🚀


<br>
<br>
<br>
<br>
<br>
<br>

이 코드에서 `#define`이 사용된 부분은 다음과 같습니다.

```cpp
#ifndef ROBOT_LOCALIZATION__UKF_HPP_
#define ROBOT_LOCALIZATION__UKF_HPP_
...
#endif  // ROBOT_LOCALIZATION__UKF_HPP_
```

이는 **헤더 가드(Header Guard)** 라고 하며, `#define`이 사용된 이유는 **헤더 파일의 중복 포함을 방지**하기 위해서입니다.

---

# **✅ 1) 헤더 가드란? (`#ifndef`, `#define`, `#endif`)**
**헤더 가드는 C/C++에서 동일한 헤더 파일이 여러 번 포함되는 것을 방지하는 기법**입니다.  
위 코드에서는 `UKF_HPP_`라는 매크로를 사용하여 중복 포함을 방지하고 있습니다.

```cpp
#ifndef ROBOT_LOCALIZATION__UKF_HPP_  // 1. 만약 ROBOT_LOCALIZATION__UKF_HPP_가 정의되지 않았다면
#define ROBOT_LOCALIZATION__UKF_HPP_  // 2. ROBOT_LOCALIZATION__UKF_HPP_를 정의하고 파일 내용을 포함
...
#endif  // ROBOT_LOCALIZATION__UKF_
```
✅ **이렇게 하면 동일한 헤더 파일이 여러 번 포함되더라도, 한 번만 처리됩니다.**

---

## **✅ 2) 왜 `#define`을 사용하는가? (`#pragma once` 대체 가능)**
C++에서는 **`#define` 대신 `#pragma once`를 사용하여 더 간결하게 헤더 가드를 구현할 수 있습니다.**

### **🔹 `#pragma once` 대체 코드 (더 좋은 방법)**
```cpp
#pragma once  // ✅ 더 간결하고 안전한 방법

#include <robot_localization/filter_base.hpp>
#include <vector>

namespace robot_localization {
    class Ukf : public FilterBase {
        ...
    };
}
```
✅ **장점:**  
- 코드가 더 간결해짐.  
- 매크로를 사용할 필요 없음.  
- 모든 컴파일러에서 지원되지는 않지만, **대부분의 최신 컴파일러(GCC, Clang, MSVC)에서는 지원됨.**  

📌 **따라서, 가능하면 `#pragma once`를 사용하고, 레거시 코드 또는 특정 컴파일러에서 호환성이 필요하면 `#ifndef ... #define`을 사용하세요.** 🚀

---

## **✅ 3) `#define`을 사용한 헤더 가드 vs `#pragma once` 비교**
| **방식** | **장점** | **단점** |
|---|---|---|
| `#ifndef ... #define` | 모든 C++ 컴파일러에서 작동 | 코드가 길어짐 |
| `#pragma once` | 코드가 간결하고 중복 포함 방지 | 일부 오래된 컴파일러에서 지원되지 않을 수도 있음 |

📌 **최신 C++ 코드에서는 `#pragma once`를 선호하는 것이 좋습니다!** 🚀
