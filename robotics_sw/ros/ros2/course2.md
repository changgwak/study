아래는 **ROS2 예제로 배우는 C++ 강좌 목차**야.  
모든 예제는 **ROS2 코드 기반**으로 작성하고, Python과 비교하여 설명하는 방식으로 진행할 수 있도록 구성했어. 🚀

---

# 📖 **ROS2 예제로 배우는 C++ 강좌 목차**
> **대상**: ROS2 기본 개념을 알고 있지만 C++이 처음인 Python 개발자  
> **목표**: C++ 문법을 ROS2 예제와 함께 익히면서 C++ 기반의 ROS2 패키지를 개발할 수 있도록 학습  

---

## **🔹 1. C++ 기본 문법 익히기 (Python과 비교)**
> **목표**: Python과 비교하여 C++ 기본 문법을 익히고, ROS2 개발에 필요한 필수 개념을 학습  
### 1-1. C++ 프로그램의 구조와 실행 방법  
- `main()` 함수 구조 (`int main(int argc, char** argv)`)  
- 헤더 파일 (`#include`)과 네임스페이스 (`using namespace std`)  
- **Python `def`와 C++ 함수 비교**  

### 1-2. 변수와 데이터 타입  
- C++ 기본 데이터 타입 (`int`, `float`, `double`, `bool`, `char`)  
- `std::string` vs. Python의 문자열  
- `auto`와 타입 자동 추론  

### 1-3. 포인터와 참조 (Python과 차이점)  
- **C++ 포인터 (`*`, `&`) vs. Python의 참조 방식**  
- 동적 메모리 할당 (`new`, `delete`, `std::shared_ptr`)  

### 1-4. 제어문과 반복문  
- 조건문 (`if`, `switch`)  
- 반복문 (`for`, `while`, `do-while`)  
- **Python `for x in list:` vs. C++ 범위 기반 `for` 문**  

### 1-5. 함수와 오버로딩  
- 함수 정의 (`returnType functionName(arguments)`)  
- 함수 오버로딩 (Python과 차이점)  

---

## **🔹 2. ROS2에서의 C++ 객체지향 프로그래밍 (OOP)**
> **목표**: ROS2 개발에서 활용하는 C++ 객체지향 개념을 익히고 적용  
### 2-1. 클래스와 객체  
- **Python 클래스와 C++ 클래스 비교**  
- 생성자 (`constructor`) & 소멸자 (`destructor`)  
- 객체 생성 방법 (스택 vs. 힙 메모리)  

### 2-2. 상속과 다형성  
- 기본 상속 (`public`, `protected`, `private`)  
- 가상 함수 (`virtual function`)  
- 추상 클래스와 인터페이스 (`pure virtual function`)  

### 2-3. 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)  
- Python `Garbage Collection`과 비교  
- ROS2에서 `std::shared_ptr` 활용  

---

## **🔹 3. C++ STL과 ROS2**
> **목표**: ROS2에서 자주 사용하는 C++ 표준 라이브러리(STL) 활용  
### 3-1. C++ 컨테이너 (배열, 벡터, 리스트)  
- `std::vector`, `std::array`, `std::list` 활용  
- Python 리스트와 C++ 컨테이너 비교  

### 3-2. C++ 맵과 해시맵 (`std::map`, `std::unordered_map`)  
- ROS2 메시지 매핑과 활용 사례  
- Python 딕셔너리와 비교  

### 3-3. C++ 알고리즘 라이브러리 (`<algorithm>`)  
- `std::sort()`, `std::find()`, `std::transform()`  
- Python `sorted()`와 비교  

---

## **🔹 4. C++ 멀티스레딩과 병렬 프로그래밍 (ROS2에서의 활용)**
> **목표**: ROS2에서의 병렬 실행 및 Executor 활용  
### 4-1. C++의 기본 멀티스레딩 (`std::thread`)  
- Python `threading`과 C++ `std::thread` 비교  
- `std::mutex`를 활용한 동기화  

### 4-2. `std::async`와 비동기 실행  
- Python `asyncio`와 C++ `std::async` 비교  

### 4-3. ROS2에서의 멀티스레딩  
- `rclcpp::executors::MultiThreadedExecutor` 사용법  
- `rclcpp::Timer`을 활용한 주기적 작업
- (심화)callback group 사용법  

---

## **🔹 5. ROS2 C++ 패키지 개발 기초**
> **목표**: ROS2 C++ 패키지 생성과 기본 기능 구현  
### 5-1. `ament_cmake` 기반 C++ 패키지 만들기  
- `CMakeLists.txt`와 `package.xml` 이해(기초)
- `CMakeLists.txt`와 `package.xml` 이해(심화)  
- Python `setup.py`와 C++ 빌드 방식 비교  

### 5-2. ROS2 C++ 노드 작성 (`rclcpp::Node`)  
- `rclcpp::Node` 기반 노드 구현  
- `ros2 run`으로 실행  

### 5-3. ROS2 퍼블리셔 & 서브스크라이버  
- `rclcpp::Publisher`와 `rclcpp::Subscription`  
- QoS 설정 (`rclcpp::QoS`)  

---

## **🔹 6. ROS2 C++ 패키지 개발 심화**
> **목표**: ROS2 C++ 고급 기능 활용  
### 6-1. ROS2 서비스와 액션 (`rclcpp::Service`, `rclcpp::Client`)  
- Python과 C++에서의 서비스 구현 차이  

### 6-2. ROS2 메시지 타입 정의 및 활용  
- `std_msgs`, `geometry_msgs` 활용  
- 커스텀 메시지 (`rosidl_generator_cpp`) 생성  

### 6-3. ROS2 TF2를 활용한 좌표 변환  
- `tf2_ros::TransformBroadcaster` & `tf2_ros::TransformListener`  

---

## **🔹 7. ROS2 C++ 고급 기능**
> **목표**: ROS2 애플리케이션 개발 시 필수 기능 익히기  
### 7-1. ROS2 로깅 및 디버깅 (`RCLCPP_INFO`)  
- Python `print()`와 C++ 로깅 비교  

### 7-2. ROS2 파라미터 서버 (`rclcpp::Parameter`)  
- 동적 파라미터 업데이트 (`rclcpp::ParameterEventHandler`)  

### 7-3. ROS2에서의 파일 입출력 (CSV, YAML, JSON)  
- `std::fstream`을 활용한 데이터 로깅  

---

## **🔹 8. ROS2 네비게이션과 SLAM을 C++로 구현 기초**
> **목표**: ROS2 Navigation2와 SLAM을 C++로 제어  
### 8-1. ROS2 Navigation2 개요 (`nav2_bringup`)  
- C++에서 `nav2_lifecycle_manager` 활용  

### 8-2. SLAM 기본 개념과 실행 (Cartographer SLAM, SLAM Toolbox)  
- SLAM 결과를 가공하여 활용  

---

## **🔹 9. ROS2 네비게이션과 SLAM을 C++로 구현 심화**
> **목표**: ROS2 경로 계획 및 최적화  
### 9-1. ROS2 C++로 경로 계획 및 이동  
- `nav_msgs::Path` 활용  
- `geometry_msgs::Pose`를 사용한 로봇 이동  

### 9-2. 성능 최적화 및 배포  
- `rclcpp::Timer`을 활용한 최적화  
- Docker를 이용한 ROS2 패키지 배포 (`ros2 cross_compile`)  

---

이제 **ROS2 기반으로 C++을 익히면서 실전 개발까지 가능한 강좌** 에 대해 알아보자.

<br>
<br>
<br>
<br>

# **🔹 1. C++ 기본 문법 익히기 (Python과 비교)**  
### **목표:**  
Python과 비교하여 C++ 기본 문법을 익히고, ROS2 개발에 필요한 필수 개념을 학습한다.

---

## **1-1. C++ 프로그램의 구조와 실행 방법**  

C++ 프로그램은 Python과 달리 **명확한 구조**를 가진다.  
Python은 파일을 실행하면 바로 코드를 실행할 수 있지만, C++은 반드시 `main()` 함수부터 실행된다.  

---

### **✅ C++의 `main()` 함수 구조**  
모든 C++ 프로그램에는 `main()` 함수가 **필수**로 포함되어야 한다.  

#### **📌 기본 구조**
```cpp
#include <iostream>  // 표준 입출력 라이브러리 포함

int main(int argc, char** argv) {  // main 함수 정의
    std::cout << "Hello, ROS2 & C++!" << std::endl;  // 표준 출력
    return 0;  // 프로그램 종료
}
```

#### **📌 코드 설명**
- `#include <iostream>` → 표준 입출력 라이브러리를 포함 (`std::cout`을 사용하기 위해 필요)
- `int main(int argc, char** argv)` → 프로그램 실행의 시작점 (`argc`, `argv`는 명령줄 인수)
- `std::cout << "Hello, ROS2 & C++!" << std::endl;` → 콘솔에 문자열 출력
- `return 0;` → 프로그램이 정상 종료됨을 의미

#### **🆚 Python과 비교**
|  | **Python** | **C++** |
|---|---|---|
| 실행 시작 위치 | 파일의 맨 위부터 실행 | `main()` 함수부터 실행 |
| 기본 함수 구조 | `def function_name():` | `int function_name() {}` |
| 프로그램 종료 | 명시적 종료 없음 | `return 0;`으로 종료 |

#### **📌 Python 코드와 비교**
```python
print("Hello, ROS2 & Python!")  # Python에서는 main 함수 없이도 실행 가능
```

💡 Python에서는 `print()`를 바로 사용할 수 있지만, C++에서는 반드시 `main()` 안에서 `std::cout`을 사용해야 한다.

---

### **✅ C++에서 명령줄 인수 사용 (`argc, argv`)**
ROS2 노드를 실행할 때 Python에서 `sys.argv`를 사용하듯, C++에서도 `argc`, `argv`를 사용하여 명령줄 인수를 받을 수 있다.

#### **📌 C++에서 명령줄 인수 사용**
```cpp
#include <iostream>

int main(int argc, char** argv) {
    std::cout << "Number of arguments: " << argc << std::endl;
    for (int i = 0; i < argc; i++) {
        std::cout << "Argument " << i << ": " << argv[i] << std::endl;
    }
    return 0;
}
```

#### **🆚 Python과 비교**
|  | **Python (`sys.argv`)** | **C++ (`argc, argv`)** |
|---|---|---|
| 명령줄 인수 저장 방식 | `sys.argv` 리스트 | `argv` 배열 (`char** argv`) |
| 인수 개수 확인 | `len(sys.argv)` | `argc` 값 |
| 첫 번째 인수 값 | `sys.argv[0]` (스크립트 이름) | `argv[0]` (프로그램 실행 파일 이름) |

#### **📌 Python 코드**
```python
import sys

print(f"Number of arguments: {len(sys.argv)}")
for i, arg in enumerate(sys.argv):
    print(f"Argument {i}: {arg}")
```

💡 **ROS2 실행 시 활용 예제**  
```bash
ros2 run my_package my_node --ros-args -p param_name:=value
```
이와 같은 명령을 실행할 때, Python에서는 `sys.argv`로, C++에서는 `argv`로 인수를 받을 수 있다.

---

## **1-2. 헤더 파일과 네임스페이스 (`#include`, `using namespace std`)**

### **✅ C++의 헤더 파일 (`#include`)**
C++은 기능별로 **헤더 파일**을 분리하여 관리한다.  
Python에서는 `import`를 사용하여 라이브러리를 불러오지만, C++에서는 `#include`를 사용하여 헤더 파일을 포함한다.

#### **📌 C++ 헤더 파일 포함 예제**
```cpp
#include <iostream>  // 표준 입출력 라이브러리
#include <vector>    // 벡터 라이브러리
#include "my_header.h"  // 사용자 정의 헤더 파일
```

#### **🆚 Python과 비교**
|  | **Python (`import`)** | **C++ (`#include`)** |
|---|---|---|
| 표준 라이브러리 사용 | `import os` | `#include <iostream>` |
| 외부 패키지 사용 | `import numpy as np` | `#include <Eigen/Dense>` |
| 사용자 정의 파일 | `import my_module` | `#include "my_header.h"` |

💡 **주의!**  
- `<iostream>` → 시스템 제공 헤더는 `< >` 사용  
- `"my_header.h"` → 사용자 정의 헤더는 `"` 사용

#### **📌 Python 코드와 비교**
```python
import sys  # 표준 라이브러리 포함
import numpy as np  # 외부 라이브러리 포함
from my_module import MyClass  # 사용자 정의 모듈 포함
```

---

### **✅ 네임스페이스 (`namespace`)**
C++에서는 같은 이름의 함수를 여러 개 정의할 수 있다.  
이름 충돌을 방지하기 위해 **네임스페이스 (namespace)** 를 사용한다.

#### **📌 네임스페이스 없이 std 사용**
```cpp
#include <iostream>

int main() {
    std::cout << "Hello, ROS2 & C++!" << std::endl;
    return 0;
}
```

💡 `std::cout` 처럼 `std::`를 붙여야 표준 라이브러리 함수(`cout`, `endl`)를 사용할 수 있다.

#### **📌 `using namespace std;` 사용**
```cpp
#include <iostream>

using namespace std;  // std 네임스페이스를 기본으로 사용

int main() {
    cout << "Hello, ROS2 & C++!" << endl;  // std:: 생략 가능
    return 0;
}
```

하지만 **대규모 프로젝트에서는 `using namespace std;`를 사용하지 않는 것이 좋다.**  
이유는 여러 라이브러리와 충돌할 가능성이 있기 때문.

💡 **ROS2에서는 `using namespace`를 사용하지 않고 `std::`를 명시적으로 쓰는 것이 권장된다.**

---

## **1-3. Python `def`와 C++ 함수 비교**
Python과 C++에서 함수를 정의하는 방법을 비교해보자.

#### **📌 C++ 함수 예제**
```cpp
#include <iostream>

void say_hello() {
    std::cout << "Hello, ROS2 & C++!" << std::endl;
}

int main() {
    say_hello();
    return 0;
}
```

#### **📌 Python 함수 예제**
```python
def say_hello():
    print("Hello, ROS2 & Python!")

say_hello()
```

#### **🆚 Python과 C++ 함수 비교**
|  | **Python** | **C++** |
|---|---|---|
| 함수 선언 방식 | `def function_name():` | `returnType function_name()` |
| 반환값이 없을 때 | `None` 반환 가능 | `void` 사용 |
| 실행 위치 | 파일 맨 위에서 바로 실행 가능 | `main()`에서 호출해야 실행 |

---

# **📌 정리**
✅ **C++ 프로그램은 `main()` 함수부터 실행**  
✅ **헤더 파일 (`#include`)을 사용하여 라이브러리 포함**  
✅ **네임스페이스 (`std::cout`)를 명시적으로 사용하는 것이 좋음**  
✅ **Python과 C++ 함수는 `def`와 `returnType function()` 형태 차이가 있음**  

이제 기본적인 C++ 프로그램 구조를 이해했으니, 다음 단계로 넘어가서 변수와 데이터 타입을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 1-2. 변수와 데이터 타입**  
> **목표:** Python과 비교하여 C++의 기본 데이터 타입을 익히고, ROS2 개발에 필요한 데이터 타입을 학습한다.

---

## **✅ C++ 기본 데이터 타입 (`int`, `float`, `double`, `bool`, `char`)**  
C++은 Python과 달리 **변수 타입을 명시적으로 선언해야** 한다.  
Python은 동적 타입(dynamic typing)을 사용하지만, C++은 정적 타입(static typing)을 사용하여 성능을 최적화한다.

---

### **📌 C++의 기본 데이터 타입**
| **데이터 타입** | **설명** | **C++ 예제** | **Python과 비교** |
|---|---|---|---|
| `int` | 정수형 (4바이트) | `int a = 42;` | `a = 42` |
| `float` | 부동소수점 (4바이트, 단정밀도) | `float b = 3.14f;` | `b = 3.14` |
| `double` | 부동소수점 (8바이트, 배정밀도) | `double c = 3.141592;` | `c = 3.141592` |
| `bool` | 참/거짓 값 (1바이트) | `bool d = true;` | `d = True` |
| `char` | 단일 문자 (1바이트) | `char e = 'A';` | `e = 'A'` |

---

### **✅ C++ 기본 데이터 타입 예제**
```cpp
#include <iostream>

int main() {
    int a = 42;            // 정수형 변수
    float b = 3.14f;       // 단정밀도 실수 (f 접미사 필요)
    double c = 3.141592;   // 배정밀도 실수
    bool d = true;         // 불리언 값 (true or false)
    char e = 'A';          // 단일 문자 (홑따옴표 사용)

    // 출력
    std::cout << "int: " << a << std::endl;
    std::cout << "float: " << b << std::endl;
    std::cout << "double: " << c << std::endl;
    std::cout << "bool: " << d << std::endl;
    std::cout << "char: " << e << std::endl;

    return 0;
}
```

💡 **Python과 비교하면?**
```python
a = 42          # 정수형
b = 3.14        # 실수형 (Python에서는 float이 기본)
c = 3.141592    # 더 정밀한 실수
d = True        # 불리언
e = 'A'         # 문자 (Python에서는 문자열)

print(f"int: {a}")
print(f"float: {b}")
print(f"double: {c}")
print(f"bool: {d}")
print(f"char: {e}")
```

### **🆚 Python과의 차이점**
1. **C++은 변수 타입을 반드시 선언해야 한다.**
2. **C++에서는 `char` 타입이 존재**하지만, Python에서는 `str` 타입으로 처리된다.
3. **C++의 `bool`은 `true`/`false`, Python의 `bool`은 `True`/`False`(대소문자 주의!).**

---

## **✅ `std::string` vs. Python의 문자열**
Python에서는 문자열이 기본적으로 `str` 타입이지만, C++에서는 **문자열을 다룰 때 `std::string`을 사용**해야 한다.

---

### **📌 C++에서 문자열 사용 (`std::string`)**
```cpp
#include <iostream>
#include <string>  // std::string을 사용하기 위해 필요

int main() {
    std::string text = "Hello, ROS2 & C++!";
    
    // 문자열 출력
    std::cout << text << std::endl;

    // 문자열 길이
    std::cout << "문자열 길이: " << text.length() << std::endl;

    // 부분 문자열 추출
    std::string sub = text.substr(7, 4);  // "ROS2"
    std::cout << "부분 문자열: " << sub << std::endl;

    return 0;
}
```

💡 **Python과 비교하면?**
```python
text = "Hello, ROS2 & Python!"

# 문자열 출력
print(text)

# 문자열 길이
print(f"문자열 길이: {len(text)}")

# 부분 문자열 추출
sub = text[7:11]  # "ROS2"
print(f"부분 문자열: {sub}")
```

### **🆚 `std::string` vs. Python `str` 차이점**
|  | **C++ (`std::string`)** | **Python (`str`)** |
|---|---|---|
| 문자열 선언 | `std::string s = "Hello";` | `s = "Hello"` |
| 길이 구하기 | `s.length()` | `len(s)` |
| 부분 문자열 | `s.substr(start, length)` | `s[start:end]` |
| 문자열 연결 | `s1 + s2` | `s1 + s2` |
| 문자 접근 | `s[i]` | `s[i]` |

**Python은 문자열을 리스트처럼 다룰 수 있지만, C++에서는 `std::string`의 메서드를 활용해야 한다.**

---

## **✅ `auto`와 타입 자동 추론**
C++11부터는 `auto` 키워드를 사용하여 **컴파일러가 변수의 타입을 자동으로 추론**할 수 있다.  
Python은 원래 동적 타입 언어이므로 `auto`와 유사한 방식으로 동작한다.

---

### **📌 `auto`를 사용한 타입 추론**
```cpp
#include <iostream>

int main() {
    auto x = 10;        // int로 추론됨
    auto y = 3.14;      // double로 추론됨
    auto z = "Hello";   // const char*로 추론됨 (문자열 리터럴)

    std::cout << "x: " << x << ", y: " << y << ", z: " << z << std::endl;

    return 0;
}
```

💡 **Python과 비교하면?**
```python
x = 10        # 자동으로 int로 결정됨
y = 3.14      # 자동으로 float로 결정됨
z = "Hello"   # 자동으로 str로 결정됨

print(f"x: {x}, y: {y}, z: {z}")
```

### **🆚 `auto` vs. Python의 동적 타입**
|  | **C++ (`auto`)** | **Python (동적 타입)** |
|---|---|---|
| 타입 선언 방식 | `auto x = 42;` | `x = 42` |
| 실행 시 타입 변경 | 변경 불가 (`auto`는 컴파일 타임에 결정) | 변경 가능 (`x = "Hello"` 가능) |
| 변수 타입 확인 | `typeid(x).name()` | `type(x)` |

🚀 **ROS2에서는 `auto`를 적극적으로 사용하여 가독성을 높일 수 있다.**  
예를 들어, **퍼블리셔에서 메시지 타입을 자동으로 추론**할 때 유용하다.

```cpp
auto publisher = node->create_publisher<std_msgs::msg::String>("chatter", 10);
```
위 코드에서 `auto`를 사용하면 `publisher`의 타입을 명시적으로 쓰지 않아도 된다.

---

## **📌 정리**
✅ **C++에서는 변수 타입을 명시적으로 선언해야 하지만, `auto`를 사용하면 자동 추론 가능**  
✅ **C++의 `std::string`과 Python의 `str`은 유사하지만, 사용 방법이 다름**  
✅ **Python의 동적 타입과 C++의 정적 타입의 차이를 이해해야 함**  
✅ **ROS2 C++ 개발에서는 `auto`를 활용하면 코드 가독성이 향상됨**  

이제 C++의 기본적인 변수와 데이터 타입을 익혔으니, 다음으로 포인터와 참조 개념을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 1-3. 포인터와 참조 (Python과 차이점)**
> **목표:** Python과 비교하여 C++의 포인터와 참조 개념을 이해하고, ROS2에서 자주 사용하는 스마트 포인터(`std::shared_ptr`)의 활용법을 익힌다.

---

## **✅ C++ 포인터 (`*`, `&`) vs. Python의 참조 방식**
Python과 C++의 가장 큰 차이 중 하나는 **메모리 관리 방식**이다.  
- **Python**은 모든 변수가 **객체의 참조(reference)**를 저장한다. (자동 메모리 관리)
- **C++**은 **포인터(pointer)**와 **참조(reference)**를 사용하여 메모리를 직접 관리할 수 있다.

---

### **📌 Python의 참조 (Reference)**
Python에서는 변수를 선언하면 **메모리 주소를 저장하는 참조(Reference)가 자동으로 관리**된다.

```python
a = 10
b = a  # 'b'는 'a'가 가리키는 같은 객체(메모리)를 참조

print(a, b)  # 10 10
b = 20       # 새로운 값을 할당하면 'b'는 새로운 객체를 참조
print(a, b)  # 10 20
```
> Python에서는 `b = a`를 실행하면 **새로운 변수 `b`가 `a`가 가리키는 같은 객체를 참조**한다.

---

### **📌 C++에서의 포인터 (`*`, `&`)**
C++에서는 포인터를 사용하여 직접 **메모리 주소를 다룰 수 있다.**
- `&` → 변수의 **주소(address)**를 가져옴  
- `*` → 포인터 변수 선언 및 **메모리 주소를 통해 값(value) 참조**  

```cpp
#include <iostream>

int main() {
    int a = 10;
    int* p = &a;  // 'p'는 'a'의 주소를 저장하는 포인터

    std::cout << "a: " << a << std::endl;      // 값 출력
    std::cout << "&a: " << &a << std::endl;    // 변수 'a'의 주소 출력
    std::cout << "p: " << p << std::endl;      // 포인터가 저장하는 주소 출력
    std::cout << "*p: " << *p << std::endl;    // 포인터를 통해 참조한 값 출력

    *p = 20;  // 포인터를 통해 값 변경
    std::cout << "a after modification: " << a << std::endl;  // 20 출력

    return 0;
}
```
### **📌 실행 결과**
```
a: 10
&a: 0x7ffee5b5c3a4
p: 0x7ffee5b5c3a4
*p: 10
a after modification: 20
```

**💡 Python에서는 변수 자체가 참조를 저장하지만, C++에서는 포인터를 직접 다뤄야 한다.**  
|  | **Python** (참조) | **C++** (포인터) |
|---|---|---|
| 변수의 주소 가져오기 | `id(a)` | `&a` |
| 변수 값 접근 | `a` | `*p` |
| 변수 값 변경 | `b = 20` (새로운 객체 할당) | `*p = 20` (메모리 값 변경) |

---

## **✅ C++ 참조자 (`&` - Reference)**
C++에서는 포인터 외에도 **참조자(reference)**를 사용하여 변수를 가리킬 수 있다.  
> 참조자는 **기존 변수를 새로운 이름으로 연결하는 개념**이다.  
> Python의 참조와 비슷하지만, C++에서는 **참조자를 변경할 수 없다.**

---

### **📌 C++의 참조 예제**
```cpp
#include <iostream>

int main() {
    int a = 10;
    int& ref = a;  // 'ref'는 'a'의 별칭(alias)

    std::cout << "a: " << a << ", ref: " << ref << std::endl;
    
    ref = 20;  // 참조를 통해 'a'의 값을 변경
    std::cout << "a after modification: " << a << std::endl;

    return 0;
}
```
### **📌 실행 결과**
```
a: 10, ref: 10
a after modification: 20
```

💡 **참조자는 한 번 연결되면 다른 변수를 가리킬 수 없다!**
```cpp
int x = 5, y = 10;
int& ref = x;
ref = y;  // 'ref'가 'y'를 가리키는 것이 아니라, 'x'의 값을 'y'로 변경
```

---

## **✅ 동적 메모리 할당 (`new`, `delete`)**
Python은 **Garbage Collector**가 자동으로 메모리를 해제하지만, C++에서는 수동으로 메모리를 관리해야 한다.  
> **동적 메모리 할당 (`new`)**: 실행 중에 메모리를 직접 할당  
> **메모리 해제 (`delete`)**: 사용이 끝난 메모리를 직접 해제  

---

### **📌 `new`와 `delete` 예제**
```cpp
#include <iostream>

int main() {
    int* p = new int(10);  // 힙(Heap)에 정수 10을 할당하고 포인터로 가리킴

    std::cout << "Allocated value: " << *p << std::endl;

    delete p;  // 할당된 메모리 해제
    p = nullptr;  // 포인터 초기화 (안전한 포인터 사용)

    return 0;
}
```
💡 **Python에서는 `a = 10`처럼 변수 선언만 하면 되지만, C++에서는 `new`와 `delete`를 사용해야 한다.**

---

## **✅ 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)**
C++11 이후로 **스마트 포인터**가 도입되어, `new`와 `delete`를 직접 사용하지 않고 메모리를 자동 관리할 수 있다.  
> **ROS2에서는 `std::shared_ptr`을 기본적으로 사용**한다.

---

### **📌 `std::shared_ptr` 예제**
```cpp
#include <iostream>
#include <memory>  // 스마트 포인터를 사용하기 위해 필요

int main() {
    std::shared_ptr<int> ptr = std::make_shared<int>(10);  // 10을 저장하는 shared_ptr

    std::cout << "Shared Pointer Value: " << *ptr << std::endl;

    return 0;  // `ptr`이 자동으로 메모리를 해제
}
```
**💡 `std::shared_ptr`는 참조 횟수(reference count)를 관리하며, 더 이상 사용되지 않으면 자동으로 메모리를 해제한다.**

---

### **✅ ROS2에서 `std::shared_ptr` 활용**
ROS2에서는 `std::shared_ptr`을 기본적으로 사용하여 **노드(Node)와 메시지(Message) 객체를 관리**한다.

#### **📌 ROS2 C++ 노드에서 `std::shared_ptr` 사용**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "Hello, ROS2 & C++!");
    }
};

int main(int argc, char** argv) {
    rclcpp::init(argc, argv);

    auto node = std::make_shared<MyNode>();  // 스마트 포인터 사용
    rclcpp::spin(node);

    rclcpp::shutdown();
    return 0;
}
```
💡 **ROS2의 `rclcpp::Node` 객체는 `std::shared_ptr`으로 관리해야 한다.**  
**메모리를 직접 관리할 필요 없이, 사용이 끝나면 자동으로 해제된다.**

---

# **📌 정리**
✅ **Python은 모든 변수를 자동으로 참조(reference)하지만, C++은 포인터(`*`), 참조(`&`), 스마트 포인터(`std::shared_ptr`)를 사용해야 한다.**  
✅ **C++에서는 `new`와 `delete`를 사용해 동적 메모리를 직접 관리해야 하지만, `std::shared_ptr`을 사용하면 자동 관리가 가능하다.**  
✅ **ROS2에서는 `std::shared_ptr`을 사용하여 노드와 메시지 객체를 관리한다.**  

이제 포인터와 메모리 관리 개념을 익혔으니, 다음으로 **C++의 제어문과 반복문**을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 1-4. C++의 제어문 (Python과 비교)**
> **목표:** Python과 비교하여 C++의 조건문과 반복문을 익히고, 범위 기반 `for` 문을 학습한다.  

---

## **✅ 조건문 (if, switch)**
조건문은 특정 조건이 참(`true`)일 때 실행되는 코드 블록을 정의하는 데 사용된다.  
C++과 Python의 `if` 문은 거의 유사하지만, `switch` 문은 Python에는 없는 C++의 고유한 기능이다.

---

### **📌 C++에서 `if` 문 사용**
C++의 `if` 문은 Python과 구조가 유사하지만, **괄호(`()`)와 중괄호(`{}`)를 반드시 사용해야 한다.**  
```cpp
#include <iostream>

int main() {
    int num = 10;

    if (num > 5) {
        std::cout << "num은 5보다 큽니다." << std::endl;
    } else if (num == 5) {
        std::cout << "num은 5입니다." << std::endl;
    } else {
        std::cout << "num은 5보다 작습니다." << std::endl;
    }

    return 0;
}
```
#### **💡 Python 코드와 비교**
```python
num = 10

if num > 5:
    print("num은 5보다 큽니다.")
elif num == 5:
    print("num은 5입니다.")
else:
    print("num은 5보다 작습니다.")
```

### **🆚 `if` 문 비교**
|  | **Python** | **C++** |
|---|---|---|
| 조건식 괄호 | 필요 없음 | **반드시 `()` 사용** |
| 코드 블록 | 들여쓰기 사용 | **`{}` 사용** |
| `else if` | `elif` 사용 | **`else if` 사용** |

---

### **📌 C++에서 `switch` 문 사용**
C++에는 Python에는 없는 `switch` 문이 있다.  
**`switch` 문은 `if-else`보다 실행 속도가 빠르고, 여러 개의 `case`를 처리할 때 유용하다.**  
```cpp
#include <iostream>

int main() {
    int num = 2;

    switch (num) {
        case 1:
            std::cout << "num은 1입니다." << std::endl;
            break;
        case 2:
            std::cout << "num은 2입니다." << std::endl;
            break;
        case 3:
            std::cout << "num은 3입니다." << std::endl;
            break;
        default:
            std::cout << "num은 1, 2, 3이 아닙니다." << std::endl;
    }

    return 0;
}
```
💡 **주의할 점:**  
- `case` 문이 끝날 때 반드시 `break;`를 사용해야 한다. (없으면 다음 `case`로 계속 실행됨)  
- `default`는 `else` 역할을 하며, **모든 `case`에 해당하지 않을 때 실행**된다.  

Python에서는 `switch` 문이 없고, `if-elif-else`로 대체해야 한다.  
```python
num = 2

if num == 1:
    print("num은 1입니다.")
elif num == 2:
    print("num은 2입니다.")
elif num == 3:
    print("num은 3입니다.")
else:
    print("num은 1, 2, 3이 아닙니다.")
```
---

## **✅ 반복문 (for, while, do-while)**
C++과 Python의 `for` 문과 `while` 문은 비슷하지만, C++에는 `do-while` 문이 추가로 존재한다.

---

### **📌 C++에서 `for` 문 사용**
C++의 `for` 문은 초기화 → 조건 검사 → 증감 연산이 포함된다.
```cpp
#include <iostream>

int main() {
    for (int i = 0; i < 5; i++) {
        std::cout << "반복 횟수: " << i << std::endl;
    }
    return 0;
}
```

#### **💡 Python 코드와 비교**
```python
for i in range(5):
    print(f"반복 횟수: {i}")
```

### **🆚 `for` 문 비교**
|  | **Python** (`range()`) | **C++** (`for`) |
|---|---|---|
| 초기화 | `for i in range(n):` | `for (int i = 0; i < n; i++)` |
| 조건 검사 | 자동 처리 | `i < n` 직접 작성 |
| 증감 연산 | 자동 처리 | `i++` 직접 작성 |

---

### **📌 C++에서 `while` 문 사용**
Python과 C++에서 `while` 문은 거의 동일하다.
```cpp
#include <iostream>

int main() {
    int i = 0;
    while (i < 5) {
        std::cout << "while 반복 횟수: " << i << std::endl;
        i++;
    }
    return 0;
}
```
#### **💡 Python 코드와 비교**
```python
i = 0
while i < 5:
    print(f"while 반복 횟수: {i}")
    i += 1
```

💡 **`while` 문은 종료 조건이 없으면 무한 루프가 발생할 수 있으므로 주의해야 한다.**

---

### **📌 C++에서 `do-while` 문 사용**
Python에는 없는 반복문으로, **최소 한 번은 실행된 후 조건을 검사**한다.
```cpp
#include <iostream>

int main() {
    int i = 0;
    do {
        std::cout << "do-while 반복 횟수: " << i << std::endl;
        i++;
    } while (i < 5);

    return 0;
}
```
💡 `do-while`은 조건을 마지막에 검사하기 때문에, **조건이 거짓이어도 최소 한 번은 실행된다.**

---

## **✅ 범위 기반 `for` 문 (`for-each`)**
Python의 `for x in list:`와 유사하게 **C++의 범위 기반 `for` 문**을 사용하면 더 간결한 코드를 작성할 수 있다.

---

### **📌 C++의 범위 기반 `for` 문**
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    for (int num : numbers) {
        std::cout << num << std::endl;
    }

    return 0;
}
```

#### **💡 Python 코드와 비교**
```python
numbers = [1, 2, 3, 4, 5]

for num in numbers:
    print(num)
```

### **🆚 `for-each` 비교**
|  | **Python** (`for x in list:`) | **C++** (범위 기반 `for`) |
|---|---|---|
| 리스트 반복 | `for x in list:` | `for (int x : list)` |
| 가독성 | 매우 직관적 | C++에서도 간결한 문법 제공 |
| 타입 명시 | 필요 없음 | 명시적 타입 필요 (`int x : list`) |

**💡 `std::vector` 같은 컨테이너와 함께 사용할 때 매우 유용하다.**

---

# **📌 정리**
✅ **C++의 `if` 문은 Python과 유사하지만, `switch` 문은 Python에 없는 기능**  
✅ **반복문(`for`, `while`)은 Python과 거의 유사하지만, `do-while` 문은 Python에 없음**  
✅ **C++의 범위 기반 `for` 문(`for-each`)는 Python의 `for x in list:`와 비슷함**  
✅ **ROS2 개발 시, `for-each` 문을 사용하면 코드가 더 간결해질 수 있음**  

이제 C++에서 **반복문과 제어문을 자유롭게 활용할 수 있다면, 다음으로 STL과 컨테이너**를 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 1-5. 함수와 오버로딩**  
> **목표:** Python과 비교하여 C++의 함수 개념과 함수 오버로딩을 익히고, ROS2 개발에 필요한 필수 개념을 학습한다.  

---

## **✅ C++에서 함수 정의 (`returnType functionName(arguments)`)**  
Python과 마찬가지로, C++에서도 **함수를 사용하여 코드의 재사용성을 높이고, 논리를 분리**할 수 있다.  
그러나, **C++ 함수는 반드시 반환 타입(`returnType`)을 명시해야 한다.**  

---

### **📌 C++ 기본 함수 구조**
```cpp
#include <iostream>

// 함수 정의
int add(int a, int b) {  // 정수 두 개를 더하는 함수
    return a + b;
}

int main() {
    int result = add(3, 5);
    std::cout << "결과: " << result << std::endl;
    return 0;
}
```
### **💡 Python 코드와 비교**
```python
# 함수 정의
def add(a, b):
    return a + b

# 함수 호출
result = add(3, 5)
print("결과:", result)
```

### **🆚 Python과 C++ 함수 비교**
|  | **Python** | **C++** |
|---|---|---|
| 함수 정의 | `def function_name():` | `returnType function_name()` |
| 반환 타입 | 자동으로 결정 (`None`, `int`, `str` 등) | 반드시 명시 (`int`, `double`, `void` 등) |
| 매개변수 타입 | 동적 타입 (런타임 결정) | 정적 타입 (컴파일 타임 결정) |
| 반환 값 없을 때 | `return None` or `pass` | `void` 사용 |

---

### **📌 C++에서 반환값이 없는 함수 (`void`)**
```cpp
#include <iostream>

// 반환값이 없는 함수
void printMessage() {
    std::cout << "Hello, ROS2 & C++!" << std::endl;
}

int main() {
    printMessage();
    return 0;
}
```
💡 **Python에서는 `return None`을 생략해도 되지만, C++에서는 `void`를 명시해야 한다.**  

---

## **✅ 함수 오버로딩 (Python과 차이점)**
함수 오버로딩(Function Overloading)이란 **같은 이름의 함수를 여러 개 정의할 수 있는 기능**이다.  
> **C++에서는 함수의 매개변수 타입이나 개수가 다르면 같은 함수 이름을 사용할 수 있지만, Python에서는 불가능하다.**

---

### **📌 C++ 함수 오버로딩 예제**
```cpp
#include <iostream>

// 정수를 더하는 함수
int add(int a, int b) {
    return a + b;
}

// 실수를 더하는 함수
double add(double a, double b) {
    return a + b;
}

// 세 개의 정수를 더하는 함수
int add(int a, int b, int c) {
    return a + b + c;
}

int main() {
    std::cout << "int add: " << add(3, 5) << std::endl;       // int 버전 호출
    std::cout << "double add: " << add(3.5, 2.2) << std::endl; // double 버전 호출
    std::cout << "three int add: " << add(1, 2, 3) << std::endl; // 세 개의 int 버전 호출
    return 0;
}
```
### **📌 실행 결과**
```
int add: 8
double add: 5.7
three int add: 6
```

#### **💡 Python 코드와 비교 (오버로딩 불가능)**
Python에서는 **같은 이름의 함수를 여러 개 정의할 수 없고, `*args`나 `type()`을 사용해야 한다.**
```python
def add(a, b, c=None):
    if c is None:
        return a + b
    return a + b + c

print("add(3, 5):", add(3, 5))
print("add(1, 2, 3):", add(1, 2, 3))
```

---

### **🆚 Python과 C++ 함수 오버로딩 비교**
|  | **Python** | **C++** |
|---|---|---|
| 함수 오버로딩 지원 | ❌ 없음 (재정의 시 마지막 함수만 사용) | ✅ 가능 (매개변수 타입, 개수로 구분) |
| 해결 방법 | `*args`, `type()` 활용 | 자동으로 적절한 함수 선택 |

💡 **C++에서는 `add(int, int)`와 `add(double, double)`을 구분할 수 있지만, Python에서는 불가능하다.**

---

## **✅ C++의 기본 매개변수 (Python의 기본 인자와 비교)**
Python에서는 기본값을 `def func(a=10):`처럼 설정할 수 있다.  
C++에서도 **기본 매개변수(Default Parameter)**를 설정할 수 있다.

---

### **📌 C++ 기본 매개변수 예제**
```cpp
#include <iostream>

// 기본값이 있는 함수
int multiply(int a, int b = 2) {  // 'b'의 기본값은 2
    return a * b;
}

int main() {
    std::cout << "multiply(3): " << multiply(3) << std::endl;   // 3 * 2 = 6
    std::cout << "multiply(3, 4): " << multiply(3, 4) << std::endl; // 3 * 4 = 12
    return 0;
}
```
💡 **기본값이 설정된 매개변수는 가장 마지막에 위치해야 한다!**
```cpp
// 오류 발생: 기본 매개변수는 뒤쪽부터 설정해야 함!
int multiply(int a = 2, int b) {  
    return a * b;
}
```

#### **💡 Python 코드와 비교**
```python
def multiply(a, b=2):
    return a * b

print(multiply(3))    # 3 * 2 = 6
print(multiply(3, 4)) # 3 * 4 = 12
```

### **🆚 Python과 C++ 기본 매개변수 비교**
|  | **Python** | **C++** |
|---|---|---|
| 기본값 설정 위치 | 어디든 가능 | **마지막 매개변수부터 설정 가능** |
| 적용 방식 | `def func(a=10, b=20):` | `int func(int a, int b=20)` |

---

## **✅ 함수 오버로딩과 ROS2 예제**
ROS2에서는 **같은 노드에서 여러 유형의 메시지를 처리해야 할 때 함수 오버로딩을 사용할 수 있다.**

### **📌 ROS2 C++에서 `std_msgs::msg::String`과 `std_msgs::msg::Int32`를 모두 처리하는 함수**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"
#include "std_msgs/msg/int32.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        // 두 개의 서로 다른 콜백 함수 정의
        sub_string = this->create_subscription<std_msgs::msg::String>(
            "string_topic", 10, std::bind(&MyNode::callback, this, std::placeholders::_1));
        
        sub_int = this->create_subscription<std_msgs::msg::Int32>(
            "int_topic", 10, std::bind(&MyNode::callback, this, std::placeholders::_1));
    }

    // 함수 오버로딩을 활용한 메시지 처리
    void callback(const std_msgs::msg::String::SharedPtr msg) {
        RCLCPP_INFO(this->get_logger(), "String message received: %s", msg->data.c_str());
    }

    void callback(const std_msgs::msg::Int32::SharedPtr msg) {
        RCLCPP_INFO(this->get_logger(), "Int message received: %d", msg->data);
    }

private:
    rclcpp::Subscription<std_msgs::msg::String>::SharedPtr sub_string;
    rclcpp::Subscription<std_msgs::msg::Int32>::SharedPtr sub_int;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();
    return 0;
}
```
💡 **C++ 함수 오버로딩을 사용하면, `std_msgs::msg::String`과 `std_msgs::msg::Int32`를 동일한 `callback` 함수에서 처리할 수 있다.**  

---

# **📌 정리**
✅ **C++에서는 반드시 `returnType`을 명시해야 한다.**  
✅ **Python에서는 함수 오버로딩이 불가능하지만, C++에서는 지원된다.**  
✅ **C++에서는 기본 매개변수를 사용할 수 있지만, 마지막 인수부터 설정해야 한다.**  
✅ **ROS2 C++에서 여러 메시지를 처리할 때 함수 오버로딩을 활용하면 편리하다.**  

이제 함수 개념을 이해했으니, 다음으로 **C++의 STL과 컨테이너를 학습해보자! 🚀**


<br>
<br>
<br>
<br>

# **🔹 2-1. 클래스와 객체**  
> **목표:** ROS2 개발에서 활용하는 C++ 객체지향 개념을 익히고, Python과 비교하여 C++에서의 클래스와 객체 개념을 쉽게 이해한다.

---

## **✅ Python 클래스 vs. C++ 클래스 비교**
Python과 C++은 모두 **객체지향 프로그래밍(OOP, Object-Oriented Programming)**을 지원한다.  
하지만 C++에서는 **클래스를 정의할 때 타입을 명확히 지정해야 하며, 메모리 관리 방식이 다르다.**  

### **📌 Python 클래스 예제**
```python
class Robot:
    def __init__(self, name, model):
        self.name = name
        self.model = model

    def introduce(self):
        print(f"Hello, I am {self.name}, model {self.model}.")

# 객체 생성
r1 = Robot("TurtleBot", "3")
r1.introduce()
```
💡 Python에서는 `self`가 필수이며, `__init__()`가 생성자 역할을 한다.

---

### **📌 C++ 클래스 예제**
```cpp
#include <iostream>
#include <string>

class Robot {
public:
    std::string name;
    std::string model;

    // 생성자 (Constructor)
    Robot(std::string robot_name, std::string robot_model) {
        name = robot_name;
        model = robot_model;
    }

    // 멤버 함수
    void introduce() {
        std::cout << "Hello, I am " << name << ", model " << model << "." << std::endl;
    }
};

int main() {
    Robot r1("TurtleBot", "3");  // 객체 생성
    r1.introduce();

    return 0;
}
```

### **🆚 Python과 C++ 클래스 비교**
|  | **Python** | **C++** |
|---|---|---|
| 클래스 선언 | `class ClassName:` | `class ClassName {}` |
| 생성자 | `__init__()` | `ClassName()` |
| 멤버 변수 | `self.name` | `name` (접근 제어자 필요) |
| 멤버 함수 | `def method(self):` | `void method() {}` |
| 객체 생성 | `obj = ClassName()` | `ClassName obj;` 또는 `ClassName* obj = new ClassName();` |

---

## **✅ 생성자 (Constructor) & 소멸자 (Destructor)**
C++에서는 **객체가 생성될 때 자동으로 실행되는 함수**를 **생성자(Constructor)** 라고 한다.  
객체가 소멸될 때 자동으로 실행되는 함수는 **소멸자(Destructor)** 라고 한다.

---

### **📌 C++ 생성자 예제**
```cpp
#include <iostream>

class Robot {
public:
    std::string name;

    // 생성자: 객체가 생성될 때 자동으로 실행됨
    Robot(std::string robot_name) {
        name = robot_name;
        std::cout << "Robot " << name << " 생성됨!" << std::endl;
    }

    // 멤버 함수
    void say_hello() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }
};

int main() {
    Robot r1("TurtleBot");  // 생성자가 자동 호출됨
    r1.say_hello();
    return 0;
}
```
**📌 실행 결과**
```
Robot TurtleBot 생성됨!
Hello, I am TurtleBot.
```

---

### **📌 C++ 소멸자 예제 (`~ClassName()`)**
소멸자는 객체가 사라질 때 자동으로 실행된다.  
- Python에서는 `__del__()`이 있지만, 잘 사용되지 않는다.  
- C++에서는 `~ClassName()` 형태로 정의하며, **동적 메모리 해제(new, delete)** 시 중요하게 사용된다.

```cpp
#include <iostream>

class Robot {
public:
    std::string name;

    // 생성자
    Robot(std::string robot_name) {
        name = robot_name;
        std::cout << "Robot " << name << " 생성됨!" << std::endl;
    }

    // 소멸자 (Destructor)
    ~Robot() {
        std::cout << "Robot " << name << " 제거됨!" << std::endl;
    }
};

int main() {
    Robot r1("TurtleBot");
    return 0;  // main() 종료 시 r1의 소멸자가 자동 호출됨
}
```

**📌 실행 결과**
```
Robot TurtleBot 생성됨!
Robot TurtleBot 제거됨!
```

---

## **✅ 객체 생성 방법 (스택 vs. 힙 메모리)**
Python에서는 객체를 생성하면 자동으로 메모리를 할당하지만, C++에서는 **스택(stack)과 힙(heap) 메모리를 선택**하여 객체를 생성할 수 있다.

---

### **📌 스택(Stack) 메모리에서 객체 생성**
```cpp
Robot r1("TurtleBot");  // 스택에 저장됨
```
- `r1`은 **스택(stack)**에 저장된다.
- 함수가 끝나면 **자동으로 메모리가 해제**된다.
- 속도가 빠르고 관리가 쉽지만, **큰 데이터를 저장하기 어렵다.**

---

### **📌 힙(Heap) 메모리에서 객체 생성 (`new` & `delete`)**
```cpp
Robot* r2 = new Robot("TurtleBot");  // 힙에 저장됨
delete r2;  // 메모리 해제
```
- `new`를 사용하면 객체가 **힙(heap)**에 저장된다.
- 명시적으로 `delete`를 호출해야 **메모리 누수를 방지**할 수 있다.
- 메모리를 더 오래 유지할 수 있지만, 직접 관리해야 한다.

---

### **🆚 스택 vs. 힙 메모리 비교**
|  | **스택(Stack)** | **힙(Heap)** |
|---|---|---|
| 객체 생성 | `ClassName obj;` | `ClassName* obj = new ClassName();` |
| 메모리 할당 | 함수 호출 시 자동 할당 | `new` 연산자로 수동 할당 |
| 메모리 해제 | 함수가 끝나면 자동 해제 | `delete`를 사용하여 수동 해제 |
| 속도 | 빠름 | 상대적으로 느림 |
| 활용 사례 | 지역 변수, 임시 객체 | 동적 객체, ROS2 스마트 포인터 |

---

## **✅ ROS2에서 C++ 클래스 활용**
ROS2에서는 **노드(Node)를 클래스로 구현**하여 관리하는 것이 일반적이다.  

---

### **📌 ROS2 C++ 노드 클래스 예제**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    // 생성자
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "노드가 생성되었습니다!");
    }

    // 소멸자
    ~MyNode() {
        RCLCPP_INFO(this->get_logger(), "노드가 제거되었습니다!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    auto node = std::make_shared<MyNode>();  // 스마트 포인터 사용
    rclcpp::spin(node);

    rclcpp::shutdown();
    return 0;
}
```
**📌 실행 결과**
```
[INFO] [my_node]: 노드가 생성되었습니다!
(노드 실행 중...)
(노드 종료 시)
[INFO] [my_node]: 노드가 제거되었습니다!
```

💡 **ROS2에서는 `std::shared_ptr`을 사용하여 객체를 관리**하면 `delete`를 명시적으로 호출하지 않아도 된다.

---

# **📌 정리**
✅ **C++ 클래스는 Python 클래스와 유사하지만, 타입을 명확히 선언해야 한다.**  
✅ **C++에서는 생성자(`ClassName()`)와 소멸자(`~ClassName()`)가 자동으로 호출된다.**  
✅ **C++에서는 스택과 힙 메모리에서 객체를 생성할 수 있으며, 힙 메모리를 사용할 때는 `delete`가 필요하다.**  
✅ **ROS2에서는 `std::shared_ptr`을 사용하여 스마트 포인터 기반으로 노드를 관리하는 것이 일반적이다.**  

이제 C++의 클래스와 객체 개념을 익혔으니, **상속과 다형성**을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 2-2. 상속과 다형성**
> **목표:** ROS2 개발에서 활용하는 C++ 객체지향 개념을 익히고, 상속과 다형성의 원리를 이해하여 ROS2 노드 클래스 설계에 적용한다.  
> **Python과 비교하면서 C++의 차이점을 강조하고, ROS2에서 실제 사용하는 예제를 포함한다.**

---

## **✅ 기본 상속 (public, protected, private)**
C++에서 **상속(Inheritance)**은 기존 클래스의 속성과 기능을 물려받아 **코드를 재사용**하는 데 사용된다.  
Python의 상속과 개념은 유사하지만, **접근 제어자(`public`, `protected`, `private`)** 가 존재하는 것이 차이점이다.

---

### **📌 Python에서의 상속 예제**
```python
class Robot:
    def __init__(self, name):
        self.name = name

    def introduce(self):
        print(f"Hello, I am {self.name}.")

# 상속된 클래스
class AutonomousRobot(Robot):
    def __init__(self, name, lidar):
        super().__init__(name)
        self.lidar = lidar

    def introduce(self):
        print(f"Hello, I am {self.name}, equipped with {self.lidar} LIDAR.")

# 객체 생성
r1 = AutonomousRobot("TurtleBot", "3D")
r1.introduce()
```
💡 Python에서는 `super().__init__(name)`을 사용하여 부모 클래스의 생성자를 호출한다.

---

### **📌 C++에서의 기본 상속**
C++에서는 `:` 뒤에 `public`, `protected`, `private`을 붙여서 상속 유형을 지정한다.
```cpp
#include <iostream>
#include <string>

// 부모 클래스 (Base Class)
class Robot {
public:
    std::string name;

    Robot(std::string robot_name) {
        name = robot_name;
    }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }
};

// 자식 클래스 (Derived Class)
class AutonomousRobot : public Robot {  // 'public'을 통해 상속
public:
    std::string lidar;

    AutonomousRobot(std::string robot_name, std::string lidar_type) 
        : Robot(robot_name), lidar(lidar_type) {}

    void introduce() {  // 함수 오버라이딩
        std::cout << "Hello, I am " << name << ", equipped with " << lidar << " LIDAR." << std::endl;
    }
};

int main() {
    AutonomousRobot r1("TurtleBot", "3D");
    r1.introduce();
    return 0;
}
```
**📌 실행 결과**
```
Hello, I am TurtleBot, equipped with 3D LIDAR.
```

---

### **✅ 상속 시 접근 제어자 (`public`, `protected`, `private`)**
C++에서 **부모 클래스의 멤버가 자식 클래스에서 어떻게 접근되는지** 결정하는 역할을 한다.

| **접근 제어자** | **설명** | **예제 코드** |
|---|---|---|
| `public` | 부모의 `public` 멤버가 자식에서도 `public`으로 유지됨 | `class Child : public Parent {}` |
| `protected` | 부모의 `public` 멤버가 자식에서는 `protected`로 변경됨 | `class Child : protected Parent {}` |
| `private` | 부모의 `public` 멤버가 자식에서는 `private`로 변경됨 | `class Child : private Parent {}` |

💡 **`private` 상속을 사용하면, 부모 클래스의 `public` 멤버도 자식 클래스에서는 `private`으로 변경되어 외부에서 접근 불가능하다.**

---

## **✅ 가상 함수 (virtual function)**
> **가상 함수(`virtual function`)는 C++에서 다형성(polymorphism)을 지원하기 위해 사용된다.**  
> **자식 클래스에서 부모 클래스의 함수를 재정의(오버라이딩)할 때 사용하며, 이를 통해 동적 바인딩(dynamic binding)이 가능해진다.**  

---

### **📌 Python에서의 다형성 예제**
Python에서는 `super().introduce()` 없이 함수 이름만 같으면 자동으로 오버라이딩된다.
```python
class Robot:
    def introduce(self):
        print("I am a generic robot.")

class AutonomousRobot(Robot):
    def introduce(self):
        print("I am an autonomous robot.")

# 다형성 적용
robots = [Robot(), AutonomousRobot()]
for robot in robots:
    robot.introduce()  # 자동으로 올바른 introduce()가 호출됨
```
📌 **Python에서는 객체 타입과 관계없이 오버라이딩된 메서드가 자동으로 호출된다.**  

---

### **📌 C++에서 가상 함수 사용**
```cpp
#include <iostream>

// 부모 클래스
class Robot {
public:
    virtual void introduce() {  // 가상 함수
        std::cout << "I am a generic robot." << std::endl;
    }
};

// 자식 클래스
class AutonomousRobot : public Robot {
public:
    void introduce() override {  // 가상 함수 오버라이딩
        std::cout << "I am an autonomous robot." << std::endl;
    }
};

int main() {
    Robot* r1 = new Robot();
    Robot* r2 = new AutonomousRobot();  // 부모 타입 포인터로 자식 객체 할당

    r1->introduce();  // "I am a generic robot."
    r2->introduce();  // "I am an autonomous robot."

    delete r1;
    delete r2;
    return 0;
}
```
**📌 실행 결과**
```
I am a generic robot.
I am an autonomous robot.
```
📌 **`virtual`을 사용하지 않으면 `r2->introduce();`에서 부모 클래스의 함수를 호출하게 된다!**

---

## **✅ 추상 클래스와 인터페이스 (`pure virtual function`)**
C++에서는 `pure virtual function`을 사용하여 **추상 클래스(abstract class)를 정의할 수 있다.**  
> 추상 클래스는 **객체를 직접 생성할 수 없고**, 반드시 자식 클래스에서 `pure virtual function`을 구현해야 한다.

---

### **📌 C++에서 추상 클래스 사용**
```cpp
#include <iostream>

// 추상 클래스
class Robot {
public:
    virtual void introduce() = 0;  // 순수 가상 함수 (pure virtual function)
};

// 자식 클래스
class AutonomousRobot : public Robot {
public:
    void introduce() override {
        std::cout << "I am an autonomous robot." << std::endl;
    }
};

int main() {
    // Robot r;  // 오류! 추상 클래스는 객체 생성 불가
    AutonomousRobot r;
    r.introduce();  // "I am an autonomous robot."
    return 0;
}
```
**📌 실행 결과**
```
I am an autonomous robot.
```
📌 `= 0`을 붙이면 **해당 함수는 반드시 자식 클래스에서 구현해야 한다.**

---

### **✅ ROS2에서 가상 함수와 추상 클래스 활용**
ROS2에서는 여러 종류의 로봇을 지원하는 공통 인터페이스를 정의할 때 추상 클래스를 활용할 수 있다.

#### **📌 ROS2에서 공통 인터페이스를 제공하는 추상 클래스**
```cpp
#include "rclcpp/rclcpp.hpp"

// 추상 클래스
class BaseRobot : public rclcpp::Node {
public:
    BaseRobot(std::string node_name) : Node(node_name) {}

    virtual void move() = 0;  // 순수 가상 함수
};

// TurtleBot 클래스 (BaseRobot 상속)
class TurtleBot : public BaseRobot {
public:
    TurtleBot() : BaseRobot("turtlebot") {}

    void move() override {
        RCLCPP_INFO(this->get_logger(), "TurtleBot is moving!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    auto robot = std::make_shared<TurtleBot>();  // 객체 생성
    robot->move();  // "TurtleBot is moving!"

    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서는 `BaseRobot` 클래스를 만들고, 각 로봇(TurtleBot, Drone 등)에서 이를 상속하여 특정 기능을 구현할 수 있다.**

---

# **📌 정리**
✅ **C++에서는 `public`, `protected`, `private` 접근 제어자를 사용하여 상속을 관리한다.**  
✅ **`virtual` 키워드를 사용하면 다형성을 적용할 수 있으며, 부모 포인터를 통해 자식 클래스의 함수를 실행할 수 있다.**  
✅ **추상 클래스(`= 0`을 포함한 가상 함수)는 인터페이스 역할을 하며, 반드시 자식 클래스에서 구현해야 한다.**  
✅ **ROS2에서는 공통 인터페이스를 정의할 때 추상 클래스를 적극적으로 활용할 수 있다.**  

다음으로 **C++의 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 활용하는 방법**을 학습해보자! 🚀



<br>
<br>
<br>
<br>

# **🔹 C++ 접근 제어자(`public`, `protected`, `private`) 비교 및 사용 사례**  
> **목표:** `public`, `protected`, `private` 접근 제어자의 차이를 이해하고, 각각을 언제 사용해야 하는지 명확히 한다.

---

## **✅ C++ 접근 제어자란?**  
C++에서는 클래스 멤버(변수 및 함수)의 접근을 제한하는 **접근 제어자(Access Specifier)**를 제공한다.  
- **`public`** → 누구나 접근 가능 (외부에서도 사용 가능)  
- **`protected`** → **자식 클래스에서만 접근 가능** (외부에서는 접근 불가)  
- **`private`** → **자식 클래스 포함, 클래스 외부에서 접근 불가**  

이 접근 제어자는 **객체의 캡슐화(Encapsulation)**를 구현하여, 불필요한 접근을 차단하고 **안전한 코드 구조를 유지하는 데 사용된다.**  

---

## **✅ `public` vs. `protected` vs. `private` 비교**
| **접근 제어자** | **같은 클래스 내부** | **자식 클래스** | **외부 객체(클래스 외부)** |
|---|---|---|---|
| `public` | ✅ 접근 가능 | ✅ 접근 가능 | ✅ 접근 가능 |
| `protected` | ✅ 접근 가능 | ✅ 접근 가능 | ❌ 접근 불가 |
| `private` | ✅ 접근 가능 | ❌ 접근 불가 | ❌ 접근 불가 |

---

## **✅ `public`, `protected`, `private` 사용 예제**
```cpp
#include <iostream>

class Robot {
public:
    std::string name;   // 누구나 접근 가능
protected:
    std::string model;  // 자식 클래스만 접근 가능
private:
    int batteryLevel;   // 내부에서만 접근 가능 (외부 및 자식 클래스 접근 불가)

public:
    Robot(std::string n, std::string m, int b) : name(n), model(m), batteryLevel(b) {}

    void showBattery() {
        std::cout << name << " 배터리 잔량: " << batteryLevel << "%" << std::endl;
    }
};

class AutonomousRobot : public Robot {
public:
    AutonomousRobot(std::string n, std::string m, int b) : Robot(n, m, b) {}

    void showModel() {
        std::cout << "모델: " << model << std::endl;  // ✅ `protected`는 자식 클래스에서 접근 가능
    }
};

int main() {
    Robot r("TurtleBot", "TB3", 80);
    std::cout << "로봇 이름: " << r.name << std::endl;  // ✅ `public`이므로 접근 가능
    r.showBattery();  // ✅ `private` 변수는 `public` 함수로 접근 가능

    AutonomousRobot ar("AutoBot", "X200", 90);
    ar.showModel();  // ✅ `protected` 변수는 자식 클래스에서 접근 가능
    // std::cout << ar.batteryLevel << std::endl;  // ❌ 오류: `private` 멤버에 접근 불가

    return 0;
}
```
### **📌 실행 결과**
```
로봇 이름: TurtleBot
TurtleBot 배터리 잔량: 80%
모델: X200
```
📌 **`public` 멤버는 자유롭게 접근 가능하지만, `protected` 멤버는 자식 클래스에서만 접근 가능하고 `private` 멤버는 클래스 내부에서만 사용할 수 있다.**  

---

## **✅ `public` 언제 사용할까?**
✅ **클래스 외부에서도 자유롭게 접근해야 하는 멤버 변수 및 함수**에 사용  
✅ **인터페이스 역할을 하는 멤버 함수**를 선언할 때 사용  
✅ **ROS2의 `Node` 클래스처럼 외부에서 접근 가능한 API를 제공할 때 사용**  

```cpp
class Robot {
public:
    std::string name;

    void sayHello() {
        std::cout << "Hello, I am " << name << "!" << std::endl;
    }
};
```
📌 **`public`을 사용하면 외부에서도 `name`과 `sayHello()`에 접근 가능하다.**

---

## **✅ `protected` 언제 사용할까?**
✅ **부모 클래스의 멤버를 자식 클래스에서는 접근해야 하지만, 외부에서는 차단해야 할 때**  
✅ **자식 클래스에서만 데이터를 활용하고 싶을 때**  
✅ **클래스 내부적으로 유지해야 할 정보가 있지만, 자식 클래스에서 수정이 필요한 경우**  

```cpp
class Robot {
protected:
    std::string model;
};

class AutonomousRobot : public Robot {
public:
    void showModel() {
        std::cout << "Model: " << model << std::endl;  // ✅ 자식 클래스에서 접근 가능
    }
};
```
📌 **`protected`를 사용하면 `model`은 자식 클래스에서만 접근 가능하고, 외부에서는 접근 불가능하다.**

---

## **✅ `private` 언제 사용할까?**
✅ **클래스 내부에서만 사용해야 하는 멤버(데이터 숨김, 정보 보호)**  
✅ **객체의 상태를 직접 수정하면 안 되는 경우 (`getter/setter`를 통해 접근해야 하는 경우)**  
✅ **ROS2에서 캡슐화(encapsulation)를 유지하면서 내부 데이터를 보호할 때**  

```cpp
class Robot {
private:
    int batteryLevel;

public:
    Robot(int battery) {
        batteryLevel = battery;
    }

    void showBattery() {
        std::cout << "Battery Level: " << batteryLevel << "%" << std::endl;
    }
};
```
📌 **`batteryLevel`은 `private`이므로 클래스 외부에서 직접 접근할 수 없으며, `showBattery()`를 통해서만 확인할 수 있다.**

---

## **✅ ROS2에서 `public`, `protected`, `private` 활용 예제**
ROS2에서는 노드(`rclcpp::Node`)를 상속받아 새로운 클래스를 만들 때 **접근 제어자를 적절히 활용**해야 한다.

```cpp
#include "rclcpp/rclcpp.hpp"

class BaseRobot : public rclcpp::Node {
protected:
    std::string model;  // 자식 클래스에서만 접근 가능

private:
    int batteryLevel;  // 클래스 내부에서만 사용 가능

public:
    BaseRobot(std::string node_name, std::string m, int battery)
        : Node(node_name), model(m), batteryLevel(battery) {}

    void showBattery() {
        RCLCPP_INFO(this->get_logger(), "Battery Level: %d%%", batteryLevel);
    }
};

class TurtleBot : public BaseRobot {
public:
    TurtleBot() : BaseRobot("turtlebot", "TB3", 80) {}

    void showModel() {
        RCLCPP_INFO(this->get_logger(), "Model: %s", model.c_str());  // ✅ `protected` 멤버 접근 가능
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto robot = std::make_shared<TurtleBot>();

    robot->showModel();   // ✅ `protected` 변수 접근 가능
    robot->showBattery(); // ✅ `public` 함수 호출 가능

    rclcpp::shutdown();
    return 0;
}
```
### **📌 실행 결과**
```
[INFO] [turtlebot]: Model: TB3
[INFO] [turtlebot]: Battery Level: 80%
```
📌 **ROS2에서 `protected`를 사용하면 자식 클래스에서 접근할 수 있지만, `private`을 사용하면 `BaseRobot` 내부에서만 데이터를 관리할 수 있다.**  

---

## **✅ 요약: 언제 `public`, `protected`, `private`을 사용할까?**
| **상황** | **사용할 접근 제어자** | **이유** |
|---|---|---|
| 외부에서 자유롭게 접근 가능한 변수나 함수 | `public` | 인터페이스 제공, API 노출 |
| 부모 클래스의 일부 멤버를 자식 클래스에서 사용해야 하는 경우 | `protected` | 외부 노출은 막고, 상속을 통한 재사용 가능 |
| 외부에서 접근하면 안 되는 멤버 | `private` | 정보 은닉(Encapsulation), 안전한 데이터 보호 |

---

# **📌 정리**
✅ **`public`은 클래스 외부에서 접근 가능하며, 인터페이스(API) 역할을 한다.**  
✅ **`protected`는 자식 클래스에서는 접근 가능하지만, 외부에서는 접근할 수 없다.**  
✅ **`private`은 클래스 내부에서만 접근 가능하며, 데이터 보호 및 정보 은닉을 위해 사용된다.**  
✅ **ROS2에서는 `protected`를 활용하여 공통 로직을 자식 노드에서 재사용할 수 있고, `private`을 이용해 중요한 데이터를 보호할 수 있다.**  

이제 **C++의 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 활용하는 방법**을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 `private` 멤버 변수와 `getter/setter`를 통한 접근 제어**  
> **목표:**  
> - `private` 멤버 변수를 직접 수정하면 안 되는 이유를 이해한다.  
> - `getter`와 `setter`를 활용하여 데이터를 안전하게 관리하는 방법을 익힌다.  
> - ROS2 개발에서 `getter/setter`를 어떻게 활용할 수 있는지 알아본다.

---

## **✅ `private` 멤버 변수의 직접 수정이 위험한 이유**  
C++에서는 **객체의 내부 상태를 보호**하기 위해 멤버 변수를 `private`으로 선언하는 것이 일반적이다.  
즉, **외부에서 직접 변수 값을 수정할 수 없도록 막고, `getter`와 `setter`를 통해 안전하게 값을 변경하도록 강제한다.**

### **📌 `private`을 사용하지 않을 때 발생하는 문제**  
```cpp
#include <iostream>

class Robot {
public:
    std::string name;
    int batteryLevel;  // ✅ public 변수 → 외부에서 직접 수정 가능

    Robot(std::string n, int b) : name(n), batteryLevel(b) {}

    void showBattery() {
        std::cout << name << " 배터리 잔량: " << batteryLevel << "%" << std::endl;
    }
};

int main() {
    Robot r1("TurtleBot", 100);
    r1.showBattery();  // ✅ 정상 출력

    // 🚨 문제 발생! 외부에서 잘못된 값 할당 가능
    r1.batteryLevel = -10;  // ❌ 배터리 값이 음수가 될 수 있음
    r1.showBattery();  // ❌ 잘못된 값이 출력됨

    return 0;
}
```
### **📌 실행 결과 (잘못된 값이 설정됨)**
```
TurtleBot 배터리 잔량: 100%
TurtleBot 배터리 잔량: -10%  // ❌ 논리적으로 잘못된 값
```

📌 **배터리 잔량(`batteryLevel`)이 음수로 설정되었음 → 잘못된 데이터가 저장됨.**  
➡ **이런 문제를 방지하려면 `private`을 사용하고, `getter`와 `setter`를 통해 값을 검증해야 한다.**

---

## **✅ `getter`와 `setter`를 활용한 데이터 보호**
`getter`와 `setter`는 **객체의 멤버 변수에 대한 읽기 및 쓰기 권한을 안전하게 관리**하는 방법이다.

- **`getter`(읽기 함수)**: `private` 변수의 값을 반환한다.
- **`setter`(쓰기 함수)**: 값이 유효한지 검증한 후 변수 값을 변경한다.

---

### **📌 `getter`와 `setter`를 사용하여 잘못된 값 방지**
```cpp
#include <iostream>

class Robot {
private:
    int batteryLevel;  // ✅ private 멤버 변수 (직접 접근 금지)

public:
    Robot(int battery) {
        setBatteryLevel(battery);  // ✅ setter를 통해 초기화
    }

    // ✅ getter (변수 값 조회)
    int getBatteryLevel() {
        return batteryLevel;
    }

    // ✅ setter (변수 값 변경)
    void setBatteryLevel(int battery) {
        if (battery < 0) {
            std::cout << "❌ 오류: 배터리 잔량은 0 이상이어야 합니다!" << std::endl;
            return;
        }
        batteryLevel = battery;
    }

    void showBattery() {
        std::cout << "배터리 잔량: " << batteryLevel << "%" << std::endl;
    }
};

int main() {
    Robot r1(100);
    r1.showBattery();  // ✅ 정상 출력

    // 🚨 잘못된 값 입력 시 자동 차단됨
    r1.setBatteryLevel(-10);  // ❌ 오류 메시지 출력
    r1.showBattery();  // ✅ 여전히 100% 유지됨

    return 0;
}
```
### **📌 실행 결과 (잘못된 값이 차단됨)**
```
배터리 잔량: 100%
❌ 오류: 배터리 잔량은 0 이상이어야 합니다!
배터리 잔량: 100%  // ✅ 잘못된 값이 반영되지 않음
```
📌 **`setBatteryLevel()`이 음수 값을 거부하므로, 데이터가 안전하게 보호된다.**  

---

## **✅ `getter/setter`와 ROS2 활용**
ROS2에서는 **로봇의 속성을 보호하고 안전하게 관리하기 위해 `getter/setter`를 많이 활용**한다.  
예를 들어, **로봇의 속도를 설정하는 `setSpeed()`를 만들고, 속도가 유효한 범위인지 검사할 수 있다.**

---

### **📌 ROS2 C++에서 `getter/setter`를 활용한 노드 설계**
```cpp
#include "rclcpp/rclcpp.hpp"

class Robot : public rclcpp::Node {
private:
    double speed;  // ✅ private 변수로 보호

public:
    Robot() : Node("robot_node"), speed(0.0) {}

    // ✅ getter (현재 속도 조회)
    double getSpeed() {
        return speed;
    }

    // ✅ setter (속도 설정)
    void setSpeed(double new_speed) {
        if (new_speed < 0.0 || new_speed > 2.0) {  // 🚨 속도 제한 (0.0 ~ 2.0 m/s)
            RCLCPP_WARN(this->get_logger(), "❌ 잘못된 속도 입력! (%.2f)", new_speed);
            return;
        }
        speed = new_speed;
        RCLCPP_INFO(this->get_logger(), "✅ 속도 설정: %.2f m/s", speed);
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto robot = std::make_shared<Robot>();

    robot->setSpeed(1.5);  // ✅ 정상 설정
    robot->setSpeed(-1.0); // ❌ 잘못된 값 (경고 출력)

    rclcpp::shutdown();
    return 0;
}
```
### **📌 실행 결과 (잘못된 값이 차단됨)**
```
[INFO] [robot_node]: ✅ 속도 설정: 1.50 m/s
[WARN] [robot_node]: ❌ 잘못된 속도 입력! (-1.00)
```
📌 **로봇의 속도(`speed`)가 `private`이므로, 외부에서 `speed`를 직접 변경할 수 없고, `setSpeed()`를 통해서만 수정할 수 있다.**  
📌 **유효하지 않은 값(-1.0)이 입력되면 경고 메시지가 출력되고, 값이 변경되지 않는다.**

---

## **✅ `getter/setter`가 필요한 상황**
| **상황** | **해결 방법** |
|---|---|
| 멤버 변수를 보호하고, 직접 수정하는 것을 방지 | `private` + `getter/setter` 사용 |
| 데이터가 특정 범위를 벗어나지 않도록 제한 | `setter`에서 검증 코드 추가 |
| ROS2에서 노드의 속성(예: 속도, 배터리 잔량)을 안전하게 관리 | `getter/setter`로 속성 값 관리 |

---

# **📌 정리**
✅ **`getter/setter`를 사용하면 `private` 변수를 보호하면서 안전한 데이터 변경이 가능하다.**  
✅ **잘못된 값이 입력되지 않도록 `setter`에서 검증할 수 있다.**  
✅ **ROS2에서는 `getter/setter`를 활용하여 로봇의 속성을 안전하게 관리하는 것이 일반적이다.**  

이제 `private` 멤버 변수를 보호하는 방법을 이해했으니, **C++의 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 활용하는 방법**을 학습해보자! 🚀


<br>
<br>
<br>
<br>

# **🔹 2-3. 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)**
> **목표:**  
> - C++ 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)의 개념을 익히고, Python의 **Garbage Collection(GC)**과 비교하여 이해한다.  
> - ROS2에서 **`std::shared_ptr`을 활용하는 방법**을 배우고, **노드(`rclcpp::Node`), 메시지(`std_msgs::msg::String`), 서비스(`std::shared_ptr` 기반)`** 등을 다룬다.

---

## **✅ Python의 Garbage Collection(GC) vs. C++의 메모리 관리**
Python과 C++은 메모리를 관리하는 방식에서 큰 차이를 보인다.  

| **언어** | **메모리 관리 방식** | **특징** |
|---|---|---|
| **Python** | **Garbage Collection (GC)** | - 자동 메모리 관리 <br> - 참조 횟수가 0이 되면 자동 해제 |
| **C++** | **수동 메모리 관리 (`new/delete`)** | - 개발자가 직접 메모리 할당 및 해제해야 함 <br> - 메모리 누수 발생 가능 |

💡 Python에서는 `del`을 사용하지 않아도 객체가 필요 없으면 자동으로 메모리가 해제되지만,  
C++에서는 `new`로 할당한 메모리는 반드시 `delete`를 호출해야 한다.

---

### **📌 Python에서 Garbage Collection 예제**
```python
class Robot:
    def __init__(self, name):
        self.name = name
        print(f"{self.name} 생성됨!")

    def __del__(self):
        print(f"{self.name} 삭제됨!")

r1 = Robot("TurtleBot")  # 객체 생성
del r1  # 객체 수동 삭제
```
**📌 실행 결과**
```
TurtleBot 생성됨!
TurtleBot 삭제됨!
```
📌 Python에서는 `del r1`을 호출하면 객체가 즉시 삭제되지만, **일반적으로 GC가 자동으로 해제**해 주므로 `del`을 직접 사용할 필요가 없다.

---

### **📌 C++에서 `new/delete`를 사용한 메모리 할당 (수동 관리)**
```cpp
#include <iostream>

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 생성됨!" << std::endl;
    }

    ~Robot() {
        std::cout << name << " 삭제됨!" << std::endl;
    }

private:
    std::string name;
};

int main() {
    Robot* r1 = new Robot("TurtleBot");  // ✅ new로 객체 동적 할당
    delete r1;  // ✅ 메모리 해제 (delete가 없으면 메모리 누수 발생)
    return 0;
}
```
**📌 실행 결과**
```
TurtleBot 생성됨!
TurtleBot 삭제됨!
```
📌 **주의!** `delete r1;`을 호출하지 않으면, `r1`의 메모리는 해제되지 않아 **메모리 누수(memory leak)**가 발생할 수 있다.  
➡ **이런 문제를 방지하기 위해 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 사용한다.**

---

## **✅ C++ 스마트 포인터 (`std::shared_ptr`, `std::unique_ptr`)**
스마트 포인터는 **자동 메모리 관리 기능을 제공하는 포인터**로, `new/delete` 없이 객체의 생명주기를 관리할 수 있다.  
C++에는 대표적으로 **두 가지 종류의 스마트 포인터**가 있다.

| **스마트 포인터 종류** | **설명** | **주요 특징** |
|---|---|---|
| `std::shared_ptr` | 여러 개의 포인터가 같은 객체를 공유할 수 있음 | **참조 횟수(Reference Count) 기반**으로 메모리를 자동 해제 |
| `std::unique_ptr` | 하나의 포인터만 객체를 소유할 수 있음 | **소유권(Ownership)이 단독**이며, 다른 포인터로 이동(`std::move()`) 가능 |

---

## **✅ `std::shared_ptr` (공유 스마트 포인터)**
> **여러 개의 `shared_ptr`가 동일한 객체를 가리킬 수 있으며, 마지막 `shared_ptr`가 소멸될 때 메모리가 해제된다.**

---

### **📌 `std::shared_ptr` 기본 사용법**
```cpp
#include <iostream>
#include <memory>  // 스마트 포인터를 사용하려면 필요

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 생성됨!" << std::endl;
    }

    ~Robot() {
        std::cout << name << " 삭제됨!" << std::endl;
    }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }

private:
    std::string name;
};

int main() {
    std::shared_ptr<Robot> r1 = std::make_shared<Robot>("TurtleBot");
    std::shared_ptr<Robot> r2 = r1;  // ✅ 같은 객체를 공유

    r1->introduce();
    r2->introduce();  // ✅ 같은 객체를 공유하므로 동일한 메모리를 참조

    return 0;  // ✅ 마지막 shared_ptr이 소멸될 때 자동으로 메모리 해제
}
```
**📌 실행 결과**
```
TurtleBot 생성됨!
Hello, I am TurtleBot.
Hello, I am TurtleBot.
TurtleBot 삭제됨!
```
📌 `r1`과 `r2`가 같은 객체를 가리키고 있으며, `r1`, `r2` 모두 소멸된 후 **자동으로 메모리 해제**된다.

---

## **✅ `std::unique_ptr` (소유권이 하나뿐인 스마트 포인터)**
> **`std::unique_ptr`은 하나의 포인터만 객체를 소유할 수 있으며, 다른 포인터로 이동(`std::move()`)해야 한다.**

---

### **📌 `std::unique_ptr` 기본 사용법**
```cpp
#include <iostream>
#include <memory>

class Robot {
public:
    Robot(std::string name) : name(name) {
        std::cout << name << " 생성됨!" << std::endl;
    }

    ~Robot() {
        std::cout << name << " 삭제됨!" << std::endl;
    }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }

private:
    std::string name;
};

int main() {
    std::unique_ptr<Robot> r1 = std::make_unique<Robot>("TurtleBot");
    // std::unique_ptr<Robot> r2 = r1;  // ❌ 오류! unique_ptr은 복사 불가

    std::unique_ptr<Robot> r2 = std::move(r1);  // ✅ 소유권 이동
    r2->introduce();  // ✅ r1은 더 이상 유효하지 않음

    return 0;  // ✅ 자동으로 메모리 해제됨
}
```
**📌 실행 결과**
```
TurtleBot 생성됨!
Hello, I am TurtleBot.
TurtleBot 삭제됨!
```
📌 **`std::unique_ptr`은 복사할 수 없으며, `std::move()`를 사용해 소유권을 이동해야 한다.**

---

## **✅ ROS2에서 `std::shared_ptr` 활용**
ROS2에서는 `std::shared_ptr`이 기본적으로 사용된다.  
노드(`rclcpp::Node`), 메시지, 서비스, 액션 등 대부분의 ROS2 객체는 **스마트 포인터 기반으로 동작**한다.

---

### **📌 ROS2 노드에서 `std::shared_ptr` 사용**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "노드가 생성되었습니다!");
    }
    ~MyNode() {
        RCLCPP_INFO(this->get_logger(), "노드가 삭제되었습니다!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    auto node = std::make_shared<MyNode>();  // ✅ 스마트 포인터 사용
    rclcpp::spin(node);  // 노드 실행

    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서는 `std::shared_ptr`을 사용하여 메모리 관리를 자동화한다.**

---

# **📌 정리**
✅ **Python은 Garbage Collection(GC)을 사용하지만, C++은 직접 메모리를 관리해야 한다.**  
✅ **C++ 스마트 포인터(`std::shared_ptr`, `std::unique_ptr`)를 사용하면 `new/delete` 없이 자동 메모리 관리가 가능하다.**  
✅ **ROS2에서는 `std::shared_ptr`을 기본적으로 사용하여 노드와 메시지를 관리한다.**  

이제 **ROS2에서 `std::shared_ptr`을 활용한 서비스와 액션 구현**을 학습해보자! 🚀


<br>
<br>
<br>

# **C++ 멤버 초기화 리스트 (`Member Initialization List`)**
> **문법:**  
> ```cpp
> ClassName(parameter_list) : member1(value1), member2(value2) { }
> ```
> **설명:**  
> **멤버 초기화 리스트**는 **클래스의 생성자에서 멤버 변수를 직접 초기화하는 방법**이다.  
> 이는 생성자 본문 내부에서 멤버 변수를 할당하는 것보다 **더 효율적이고 최적화된 방식**이다.

---

## **✅ 멤버 초기화 리스트란?**
C++에서는 **생성자의 초기화 방식**으로 두 가지 방법이 있다.
1. **생성자 본문에서 할당** → 기존 방식 (덜 효율적)
2. **멤버 초기화 리스트 사용** → 최적화된 방식 (권장)

---

## **✅ 기존 방식: 생성자 본문에서 초기화**
```cpp
#include <iostream>

class Robot {
private:
    std::string name;

public:
    Robot(std::string robot_name) {  // 생성자
        name = robot_name;  // ✅ 생성자 본문에서 할당 (덜 효율적)
    }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }
};

int main() {
    Robot r("TurtleBot");
    r.introduce();
    return 0;
}
```
📌 **이 방식은 `name = robot_name;`이 실행될 때**
1. **`name`이 먼저 기본 생성자로 초기화됨**  
2. **그 후 다시 `robot_name`으로 값을 대입함 (불필요한 초기화 발생)**  
➡ **즉, 두 번의 초기화가 일어나기 때문에 비효율적이다.**  

---

## **✅ 멤버 초기화 리스트 사용 (더 효율적인 방식)**
```cpp
#include <iostream>

class Robot {
private:
    std::string name;

public:
    // ✅ 멤버 초기화 리스트를 사용하여 초기화
    Robot(std::string robot_name) : name(robot_name) { }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }
};

int main() {
    Robot r("TurtleBot");
    r.introduce();
    return 0;
}
```
📌 **이 방식은**  
1. **`name(robot_name)`을 통해 한 번에 초기화됨**  
2. **불필요한 기본 생성자 호출이 없음 (최적화됨)**  
➡ **객체의 생성 속도가 더 빠르고, 메모리 낭비가 없음!** 🚀

---

## **✅ 멤버 초기화 리스트의 문법**
```cpp
ClassName(parameter_list) : member1(value1), member2(value2) { }
```
- `parameter_list` → 생성자의 매개변수 목록
- `member1(value1), member2(value2)` → 멤버 변수 `member1`, `member2`를 초기화

---

## **✅ 멤버 초기화 리스트의 장점**
| **방식** | **초기화 방식** | **특징** |
|---|---|---|
| 생성자 본문에서 할당 | `name = robot_name;` | **기본 생성자가 먼저 실행**된 후 값이 할당됨 (비효율적) |
| 멤버 초기화 리스트 사용 | `name(robot_name)` | **한 번에 초기화되므로 불필요한 연산이 없음 (최적화됨)** |

---

## **✅ 멤버 초기화 리스트가 필수적인 경우**
다음 경우에는 **멤버 초기화 리스트를 반드시 사용해야 한다.**

### **📌 1. `const` 멤버 변수 초기화**
```cpp
class Robot {
private:
    const std::string name;  // ✅ const 멤버 변수

public:
    // ✅ 반드시 초기화 리스트를 사용해야 함
    Robot(std::string robot_name) : name(robot_name) { }

    void introduce() {
        std::cout << "Hello, I am " << name << "." << std::endl;
    }
};
```
📌 `const` 멤버 변수는 **한 번 초기화되면 값을 변경할 수 없기 때문에**, 생성자 내부에서 `name = robot_name;`처럼 대입할 수 없다.  
➡ 따라서 **초기화 리스트를 통해 한 번에 값을 설정해야 한다.**

---

### **📌 2. `reference` 멤버 변수 초기화**
```cpp
class Robot {
private:
    std::string& model;  // ✅ 참조 변수

public:
    Robot(std::string& robot_model) : model(robot_model) { }

    void showModel() {
        std::cout << "Model: " << model << std::endl;
    }
};
```
📌 `std::string& model;`처럼 **참조 변수(`&`)**는 생성자 내부에서 다시 할당할 수 없으므로 **초기화 리스트를 사용해야 한다.**  

---

### **📌 3. 부모 클래스 생성자 호출 (`Base Class Initialization`)**
📌 **부모 클래스의 생성자를 호출할 때도 반드시 초기화 리스트를 사용해야 한다.**
```cpp
class BaseRobot {
public:
    BaseRobot(std::string type) {
        std::cout << "BaseRobot 생성됨: " << type << std::endl;
    }
};

// ✅ 초기화 리스트를 사용하여 부모 클래스 생성자 호출
class TurtleBot : public BaseRobot {
public:
    TurtleBot(std::string type) : BaseRobot(type) {
        std::cout << "TurtleBot 생성됨!" << std::endl;
    }
};

int main() {
    TurtleBot tb("Autonomous Robot");
    return 0;
}
```
📌 **부모 클래스(`BaseRobot`)의 생성자를 직접 호출하는 경우, 초기화 리스트를 반드시 사용해야 한다.**  

---

## **✅ 멤버 초기화 리스트와 ROS2**
ROS2에서는 **노드 클래스(`rclcpp::Node`)를 상속할 때 초기화 리스트를 반드시 사용**해야 한다.

### **📌 ROS2 노드에서 초기화 리스트 사용 예제**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    // ✅ 부모 클래스의 생성자를 초기화 리스트에서 호출
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "노드가 생성되었습니다!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MyNode>();  // ✅ 스마트 포인터 사용
    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서는 `rclcpp::Node` 생성자를 직접 호출해야 하므로, 초기화 리스트를 필수적으로 사용해야 한다.**  

---

## **📌 정리**
✅ **C++ 멤버 초기화 리스트(`: member(value)`)를 사용하면 객체를 최적화된 방식으로 초기화할 수 있다.**  
✅ **생성자 본문에서 할당하는 것보다, 멤버 초기화 리스트를 사용하면 불필요한 연산이 줄어든다.**  
✅ **특히 `const`, `reference`, 부모 클래스 생성자 호출 시에는 반드시 멤버 초기화 리스트를 사용해야 한다.**  
✅ **ROS2에서는 `rclcpp::Node`를 초기화할 때 멤버 초기화 리스트가 필수적으로 사용된다.**  

📌 이제 C++의 객체 초기화 개념을 완벽히 이해했으니, **다음으로 ROS2에서 노드 간 통신(`rclcpp::Publisher`, `rclcpp::Subscription`)을 다뤄보자! 🚀**


<br>
<br>
<br>
<br>

# **🔹 ROS2에서 `std::shared_ptr`을 활용한 서비스와 액션 구현**  
> **목표:**  
> - **C++의 `std::shared_ptr`을 활용하여 ROS2에서 서비스(`Service`), 액션(`Action`)을 구현하는 방법을 익힌다.**  
> - **서비스와 액션의 차이를 이해하고, 예제를 통해 실습할 수 있도록 한다.**  

---

## **✅ 1. ROS2에서 서비스(`Service`)와 액션(`Action`)의 차이**
ROS2에서는 **노드 간 요청-응답 통신을 수행하는 두 가지 방식**이 있다.  
| **기능** | **서비스 (`Service`)** | **액션 (`Action`)** |
|---|---|---|
| **사용 목적** | 빠른 요청-응답 처리 | **장시간 걸리는 작업 수행** |
| **통신 방식** | 요청(Request) → 응답(Response) | 목표 설정 → 피드백 주면서 진행 |
| **대표적 사용 사례** | 배터리 상태 확인, 센서 값 요청 | 로봇 이동 명령, 복잡한 경로 계획 |
| **구성 요소** | `Client`, `Server` | `Action Client`, `Action Server` |
| **스마트 포인터 사용** | `std::shared_ptr` 사용 | `std::shared_ptr` 사용 |

📌 **서비스는 "짧은 요청-응답"이 필요할 때 사용하고, 액션은 "오랜 시간이 걸리는 작업"을 수행할 때 사용한다.**

---

## **✅ 2. `std::shared_ptr`을 활용한 ROS2 서비스(`Service`) 구현**
### **📌 1) 서비스 서버 (`Service Server`) 만들기**
서비스 서버는 **클라이언트 요청을 받고, 응답을 반환하는 역할**을 한다.  
📌 **사용할 메시지 타입: `example_interfaces::srv::AddTwoInts`**  
```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"  // 서비스 메시지 타입

class AddTwoIntsServer : public rclcpp::Node {
public:
    AddTwoIntsServer() : Node("add_two_ints_server") {
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&AddTwoIntsServer::handle_request, this, std::placeholders::_1, std::placeholders::_2)
        );
        RCLCPP_INFO(this->get_logger(), "서비스 서버 시작됨!");
    }

private:
    // ✅ `std::shared_ptr`을 활용한 서비스 요청 처리
    void handle_request(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) 
    {
        response->sum = request->a + request->b;
        RCLCPP_INFO(this->get_logger(), "받은 요청: %d + %d = %d", request->a, request->b, response->sum);
    }

    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<AddTwoIntsServer>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **핵심 포인트:**  
✅ `std::shared_ptr<example_interfaces::srv::AddTwoInts::Request>`을 사용하여 요청 데이터를 안전하게 처리한다.  
✅ `std::shared_ptr<example_interfaces::srv::AddTwoInts::Response>`을 사용하여 응답을 반환한다.  
✅ `create_service<>()`를 이용하여 서비스 서버를 생성하고, 콜백 함수에서 요청을 처리한다.  

---

### **📌 2) 서비스 클라이언트 (`Service Client`) 만들기**
서비스 클라이언트는 **서버에게 요청을 보내고 응답을 기다리는 역할**을 한다.  
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

        while (!client_->wait_for_service(std::chrono::seconds(1))) {
            RCLCPP_WARN(this->get_logger(), "서비스를 기다리는 중...");
        }

        auto future = client_->async_send_request(request);
        if (rclcpp::spin_until_future_complete(this->get_node_base_interface(), future) ==
            rclcpp::FutureReturnCode::SUCCESS) {
            RCLCPP_INFO(this->get_logger(), "응답 받음: %d", future.get()->sum);
        } else {
            RCLCPP_ERROR(this->get_logger(), "서비스 호출 실패!");
        }
    }

private:
    rclcpp::Client<example_interfaces::srv::AddTwoInts>::SharedPtr client_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto client = std::make_shared<AddTwoIntsClient>();
    client->send_request(3, 5);
    rclcpp::shutdown();
    return 0;
}
```
📌 **핵심 포인트:**  
✅ `create_client<>()`를 사용하여 서비스 클라이언트를 생성한다.  
✅ `std::shared_ptr`를 활용하여 요청 데이터를 안전하게 관리한다.  
✅ `async_send_request()`를 사용하여 비동기 요청을 보낸다.  

---

## **✅ 3. `std::shared_ptr`을 활용한 ROS2 액션(`Action`) 구현**
### **📌 1) 액션 서버 (`Action Server`) 만들기**
액션 서버는 **긴 작업을 수행하고, 중간 피드백을 제공하며, 최종 결과를 반환**한다.  
📌 **사용할 메시지 타입: `action_tutorials_interfaces::action::Fibonacci`**  
```cpp
#include "rclcpp/rclcpp.hpp"
#include "rclcpp_action/rclcpp_action.hpp"
#include "action_tutorials_interfaces/action/fibonacci.hpp"

class FibonacciActionServer : public rclcpp::Node {
public:
    using Fibonacci = action_tutorials_interfaces::action::Fibonacci;
    using GoalHandle = rclcpp_action::ServerGoalHandle<Fibonacci>;

    FibonacciActionServer() : Node("fibonacci_action_server") {
        action_server_ = rclcpp_action::create_server<Fibonacci>(
            this,
            "fibonacci",
            std::bind(&FibonacciActionServer::handle_goal, this, std::placeholders::_1, std::placeholders::_2),
            std::bind(&FibonacciActionServer::handle_cancel, this, std::placeholders::_1),
            std::bind(&FibonacciActionServer::handle_accepted, this, std::placeholders::_1)
        );
        RCLCPP_INFO(this->get_logger(), "액션 서버 시작됨!");
    }

private:
    rclcpp_action::Server<Fibonacci>::SharedPtr action_server_;

    // ✅ 액션 요청을 받았을 때 처리
    rclcpp_action::GoalResponse handle_goal(const rclcpp_action::GoalUUID &, std::shared_ptr<const Fibonacci::Goal> goal) {
        RCLCPP_INFO(this->get_logger(), "Fibonacci 목표: %d", goal->order);
        return rclcpp_action::GoalResponse::ACCEPT_AND_EXECUTE;
    }

    // ✅ 액션 취소 요청 처리
    rclcpp_action::CancelResponse handle_cancel(const std::shared_ptr<GoalHandle> goal_handle) {
        RCLCPP_INFO(this->get_logger(), "액션 취소 요청 받음!");
        return rclcpp_action::CancelResponse::ACCEPT;
    }

    // ✅ 액션을 실행하는 함수
    void handle_accepted(const std::shared_ptr<GoalHandle> goal_handle) {
        std::thread([this, goal_handle]() {
            auto feedback = std::make_shared<Fibonacci::Feedback>();
            auto result = std::make_shared<Fibonacci::Result>();

            for (int i = 1; i <= goal_handle->get_goal()->order; i++) {
                feedback->sequence.push_back(i);
                goal_handle->publish_feedback(feedback);
            }

            result->sequence = feedback->sequence;
            goal_handle->succeed(result);
        }).detach();
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<FibonacciActionServer>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2 액션 서버는 `std::shared_ptr`을 활용하여 긴 작업을 안전하게 관리한다.** 🚀



<br>
<br>
<br>
<br>

# **🔹 ROS2에서 `std::bind`와 `std::placeholders` 활용 예제**
> **목표:**  
> - C++의 `std::bind`와 `std::placeholders`가 ROS2에서 어떻게 활용되는지 이해한다.  
> - 다양한 ROS2 예제를 통해 `std::bind`의 실전 활용법을 익힌다.  

---

## **✅ `std::bind`란?**
C++의 `std::bind`는 **멤버 함수를 특정 인자와 함께 바인딩하여, 다른 함수에서 호출할 수 있도록 하는 기능**을 제공한다.  
ROS2에서는 `std::bind`를 **콜백 함수와 함께 사용**하여 `this`(현재 클래스 인스턴스)를 전달하고,  
함수에 필요한 인수를 `std::placeholders::_1`, `std::placeholders::_2` 등의 자리 표시자로 대체한다.

---

## **✅ `std::bind`의 기본 사용법**
### **📌 1) 기본적인 `std::bind` 예제**
```cpp
#include <iostream>
#include <functional>  // ✅ std::bind 사용을 위한 헤더 파일

class MyClass {
public:
    void printMessage(int number) {
        std::cout << "Number: " << number << std::endl;
    }
};

int main() {
    MyClass obj;

    // ✅ std::bind를 사용하여 멤버 함수 바인딩
    auto boundFunction = std::bind(&MyClass::printMessage, &obj, std::placeholders::_1);

    boundFunction(42);  // ✅ 인자로 42를 전달
    return 0;
}
```
**📌 실행 결과**
```
Number: 42
```
📌 **핵심 포인트:**  
✅ `std::bind(&MyClass::printMessage, &obj, std::placeholders::_1);`  
➡ `MyClass`의 `printMessage()` 멤버 함수를 `obj` 객체에 바인딩하여 실행 가능하게 만듦.  
➡ `std::placeholders::_1`은 `printMessage()`의 첫 번째 인수(42)를 받아 실행한다.  

---

## **✅ ROS2에서 `std::bind` 사용 예제**
### **📌 2) ROS2에서 `std::bind`를 활용한 서비스 서버**
**ROS2 서비스에서는 `std::bind`를 사용하여 요청을 처리하는 콜백을 연결한다.**  
```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class AddTwoIntsServer : public rclcpp::Node {
public:
    AddTwoIntsServer() : Node("add_two_ints_server") {
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&AddTwoIntsServer::handle_request, this, std::placeholders::_1, std::placeholders::_2)
        );
        RCLCPP_INFO(this->get_logger(), "서비스 서버 시작됨!");
    }

private:
    void handle_request(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) 
    {
        response->sum = request->a + request->b;
        RCLCPP_INFO(this->get_logger(), "받은 요청: %d + %d = %d", request->a, request->b, response->sum);
    }

    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<AddTwoIntsServer>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **핵심 포인트:**  
✅ `std::bind(&AddTwoIntsServer::handle_request, this, std::placeholders::_1, std::placeholders::_2);`  
➡ `handle_request()`를 서비스의 콜백 함수로 설정  
➡ `std::placeholders::_1` → 요청 메시지, `std::placeholders::_2` → 응답 메시지를 받음  

---

### **📌 3) ROS2에서 `std::bind`를 활용한 퍼블리셔 & 서브스크라이버**
**ROS2의 퍼블리셔와 서브스크라이버에서 `std::bind`를 활용하는 예제이다.**

#### **(1) 퍼블리셔 (`Publisher`) 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MinimalPublisher : public rclcpp::Node {
public:
    MinimalPublisher() : Node("minimal_publisher"), count_(0) {
        publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);

        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&MinimalPublisher::timer_callback, this)  // ✅ `this` 바인딩
        );
    }

private:
    void timer_callback() {
        auto message = std_msgs::msg::String();
        message.data = "Hello, ROS2! Count: " + std::to_string(count_++);
        RCLCPP_INFO(this->get_logger(), "Publishing: '%s'", message.data.c_str());
        publisher_->publish(message);
    }

    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
    size_t count_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MinimalPublisher>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **핵심 포인트:**  
✅ `std::bind(&MinimalPublisher::timer_callback, this)`  
➡ `timer_callback()`을 타이머 이벤트로 등록  

---

#### **(2) 서브스크라이버 (`Subscriber`) 예제**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class MinimalSubscriber : public rclcpp::Node {
public:
    MinimalSubscriber() : Node("minimal_subscriber") {
        subscription_ = this->create_subscription<std_msgs::msg::String>(
            "chatter", 10,
            std::bind(&MinimalSubscriber::topic_callback, this, std::placeholders::_1)  // ✅ `this` 바인딩
        );
    }

private:
    void topic_callback(const std_msgs::msg::String::SharedPtr msg) {
        RCLCPP_INFO(this->get_logger(), "받은 메시지: '%s'", msg->data.c_str());
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
📌 **핵심 포인트:**  
✅ `std::bind(&MinimalSubscriber::topic_callback, this, std::placeholders::_1);`  
➡ `topic_callback()`을 콜백으로 등록  
➡ `std::placeholders::_1` → 메시지를 받을 자리  

---

## **✅ `std::bind`의 다양한 ROS2 활용 사례 정리**
| **ROS2 기능** | **콜백 함수 등록 방식** |
|---|---|
| **서비스 서버** | `std::bind(&Class::handle_request, this, std::placeholders::_1, std::placeholders::_2)` |
| **퍼블리셔의 타이머 콜백** | `std::bind(&Class::timer_callback, this)` |
| **서브스크라이버의 메시지 콜백** | `std::bind(&Class::topic_callback, this, std::placeholders::_1)` |
| **액션 서버의 실행 콜백** | `std::bind(&Class::execute_callback, this, std::placeholders::_1)` |

---

# **📌 정리**
✅ `std::bind`는 멤버 함수를 바인딩하여 콜백으로 사용할 수 있도록 한다.  
✅ `std::placeholders::_1`, `_2` 등을 활용하여 매개변수를 동적으로 전달할 수 있다.  
✅ ROS2에서는 **서비스, 퍼블리셔, 서브스크라이버, 액션 서버에서 `std::bind`를 필수적으로 활용**한다.  
✅ `this`를 전달하여 **클래스 내부 멤버 함수와 객체를 연결**할 수 있다.  

이제 `std::bind`를 자유롭게 사용할 수 있으니, **ROS2 액션 서버와 클라이언트 구현**을 더 깊이 있게 학습해 보자! 🚀

<br>
<br>
<br>

# **🔹 `private` 영역에서 `SharedPtr`이 사용되는 이유 (`rclcpp::Publisher`, `rclcpp::TimerBase`)**
> **질문:**  
> - `private` 영역에 `rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;`  
> - `private` 영역에 `rclcpp::TimerBase::SharedPtr timer_;`  
> **위 코드가 항상 들어가는 이유는 무엇이고, 어떤 문법인지?**

---

# **✅ 1) 사용된 문법 분석**
### **📌 1. `rclcpp::Publisher<T>::SharedPtr` 문법**
```cpp
rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
```
📌 **이 변수는 ROS2에서 `std_msgs::msg::Float32MultiArray` 타입의 메시지를 퍼블리시하는 `publisher_`를 저장하는 포인터**  
📌 **`SharedPtr`은 C++의 `std::shared_ptr`을 기반으로 하는 스마트 포인터**  

---

### **📌 2. `rclcpp::TimerBase::SharedPtr` 문법**
```cpp
rclcpp::TimerBase::SharedPtr timer_;
```
📌 **이 변수는 `rclcpp::create_wall_timer()`를 사용하여 생성된 타이머 객체를 저장하는 포인터**  
📌 **타이머가 `nullptr`이 되면 타이머가 자동으로 삭제되므로 `SharedPtr`을 사용하여 유지해야 함**  

---

# **✅ 2) 왜 `private` 멤버 변수로 선언하는가?**
> **OOP(Object-Oriented Programming) 원칙에 따라, 퍼블리셔와 타이머를 클래스의 `private` 멤버 변수로 선언하는 이유**  

### **✅ 1) 객체의 수명을 관리하기 위해 `SharedPtr`을 사용**
- ROS2에서 `create_publisher()`와 `create_wall_timer()`는 **스마트 포인터(`std::shared_ptr`)를 반환**함.
- `SharedPtr`은 **객체를 자동으로 관리**하며, 더 이상 사용되지 않으면 메모리가 해제됨.

```cpp
publisher_ = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", 10);
timer_ = this->create_wall_timer(
    std::chrono::seconds(1),
    std::bind(&SensorPublisher::publish_data, this)
);
```
📌 **`publisher_`와 `timer_`가 클래스 내부에 저장되지 않으면, 생성 후 바로 삭제될 수 있음!**  

---

### **✅ 2) 퍼블리셔와 타이머를 유지해야 하기 때문**
- **ROS2에서 `Publisher`와 `Timer`는 `SharedPtr`로 유지해야만 동작 가능!**  
- **로컬 변수로 선언하면, 함수 종료 후 객체가 삭제되므로 정상 동작하지 않음.**

#### **📌 잘못된 코드 (로컬 변수 사용)**
```cpp
void create_publisher_and_timer() {
    auto publisher = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", 10);
    auto timer = this->create_wall_timer(
        std::chrono::seconds(1),
        std::bind(&SensorPublisher::publish_data, this)
    );
}  // ❌ 함수가 끝나면 `publisher`와 `timer`가 삭제됨
```
📌 **함수 내에서 로컬 변수로 선언하면, 함수가 종료될 때 `publisher`와 `timer`가 삭제됨!**  
📌 **퍼블리셔와 타이머는 `private` 멤버 변수로 저장해야 지속적으로 유지됨.**  

---

# **✅ 3) `SharedPtr`을 사용하는 이유 (메모리 관리)**
ROS2는 **C++의 스마트 포인터(`std::shared_ptr`)를 활용하여 노드 내부 객체를 관리**한다.

### **📌 스마트 포인터가 필요한 이유**
1. **메모리 누수를 방지**: 수동으로 `delete`할 필요 없이 자동 관리됨.
2. **객체의 수명 관리**: 여러 곳에서 참조 가능 (`std::shared_ptr`이 존재하는 한 객체가 유지됨).
3. **안전한 동시 접근**: ROS2에서는 여러 개의 `Executor`가 병렬로 실행될 수 있음.

---

### **✅ `std::shared_ptr` 사용 예제**
```cpp
#include <memory>

class MyClass {
public:
    std::shared_ptr<int> value_;

    MyClass(int v) {
        value_ = std::make_shared<int>(v);
    }
};

int main() {
    auto obj = std::make_shared<MyClass>(10);
    std::cout << "Value: " << *obj->value_ << std::endl;
}
```
📌 **`std::shared_ptr`를 사용하면 `value_`가 자동으로 관리되어 메모리 해제 불필요.**  
📌 **ROS2에서도 동일한 방식으로 퍼블리셔와 타이머를 유지함.**

---

# **✅ 4) `private`에 선언하는 이유 (OOP 원칙)**
> **퍼블리셔와 타이머를 `private`에 선언하는 이유는?**  

### **✅ 1) 캡슐화 (Encapsulation)**
- 퍼블리셔와 타이머는 **클래스 내부에서만 사용해야 하는 요소**이므로 `private`로 선언.
- 다른 코드에서 직접 수정되지 않도록 보호.

```cpp
private:
    rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
```
📌 **이렇게 하면 `SensorPublisher` 클래스 내부에서만 접근 가능하며, 안전하게 관리할 수 있음.**  

---

### **✅ 2) 클래스가 노드 실행을 완전하게 관리하도록 설계**
```cpp
class SensorPublisher : public rclcpp::Node {
public:
    SensorPublisher() : Node("sensor_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", 10);
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&SensorPublisher::publish_data, this)
        );
    }

private:
    void publish_data() {
        auto message = std_msgs::msg::Float32MultiArray();
        message.data = {1.1, 2.2, 3.3};
        publisher_->publish(message);
    }

    rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
📌 **이렇게 하면 `SensorPublisher` 객체가 생성되는 동안 퍼블리셔와 타이머가 유지되며, 클래스가 삭제될 때 자동으로 해제됨.**

---

# **✅ 결론**
✅ **`private` 영역에 `SharedPtr`로 퍼블리셔와 타이머를 선언하는 이유는?**  
1. **객체의 수명 유지**: 함수 내 로컬 변수로 선언하면 사라질 수 있기 때문에 `private` 멤버 변수로 저장.
2. **메모리 자동 관리**: `std::shared_ptr`을 사용하여 객체가 자동으로 해제되도록 함.
3. **OOP 원칙 준수**: 퍼블리셔와 타이머는 클래스 내부에서만 사용해야 하므로 `private`로 보호.
4. **ROS2의 노드 동작 유지**: 퍼블리셔와 타이머는 `SharedPtr`을 통해 지속적으로 유지되지 않으면 동작하지 않음.

📌 **따라서, ROS2에서 `publisher_`와 `timer_`는 `private` 멤버 변수로 선언하고, `SharedPtr`을 사용하여 객체를 유지하는 것이 필수적이다!** 🚀

<br>
<br>

# **🔹 ROS2 클래스에서 `public`과 `private`의 역할과 코드 구조**
> **질문:**  
> 1. **`public` 영역에는 보통 어떤 것이 정의되는가?**  
> 2. **`private` 영역에는 보통 어떤 것이 정의되는가?**  
> 3. **ROS2 코드 구조적으로 어떻게 설계하는 것이 좋은가?**  

---

# **✅ 1) `public` vs `private`의 역할**
**ROS2의 클래스에서 `public`과 `private`는 객체지향 프로그래밍(OOP)의 **캡슐화(encapsulation) 원칙을 따른다.**  

| **영역** | **주요 내용** | **설명** |
|---|---|---|
| **`public`** | 생성자, 소멸자, 외부에서 호출 가능한 함수 | 노드 실행, 설정 변경, 외부와 인터페이스하는 기능 |
| **`private`** | 퍼블리셔, 서브스크라이버, 서비스, 타이머, 내부 함수 및 데이터 | 노드 내부에서만 사용되는 기능 및 변수 |

📌 **즉, `public`은 외부에서 접근 가능한 인터페이스를 제공하고, `private`은 노드 내부 로직을 관리하는 데 사용된다.**

---

# **✅ 2) `public`과 `private`를 활용한 ROS2 코드 예제**
> **ROS2 C++ 노드에서 `public`과 `private`을 올바르게 사용하는 코드 예제**

### **📌 예제: ROS2에서 센서 데이터를 퍼블리시하는 노드**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/float32_multi_array.hpp"

class SensorPublisher : public rclcpp::Node {
public:
    // ✅ `public`: 노드 생성자 및 외부에서 호출 가능한 함수
    SensorPublisher();
    void set_publish_rate(double rate);  // ✅ publish 주기를 변경하는 `public` 메서드

private:
    // ✅ `private`: 내부에서만 사용하는 함수
    void publish_data();

    // ✅ `private`: 내부 변수 (퍼블리셔, 타이머, 설정 값)
    rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
    double publish_rate_;  // 초당 몇 번 퍼블리시할지 저장
};

// ✅ 생성자에서 초기화
SensorPublisher::SensorPublisher() : Node("sensor_publisher"), publish_rate_(1.0) {
    publisher_ = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", 10);
    timer_ = this->create_wall_timer(
        std::chrono::duration<double>(publish_rate_),
        std::bind(&SensorPublisher::publish_data, this)
    );
}

// ✅ `public` 메서드: publish 주기 변경
void SensorPublisher::set_publish_rate(double rate) {
    if (rate > 0) {
        publish_rate_ = rate;
        timer_->reset();  // 타이머 재설정 (ROS2 Humble 이상 지원)
        RCLCPP_INFO(this->get_logger(), "Publish rate changed to %.2f Hz", rate);
    } else {
        RCLCPP_WARN(this->get_logger(), "Invalid publish rate. Keeping current rate.");
    }
}

// ✅ `private` 메서드: 센서 데이터 퍼블리시
void SensorPublisher::publish_data() {
    auto message = std_msgs::msg::Float32MultiArray();
    message.data = {1.1, 2.2, 3.3};
    RCLCPP_INFO(this->get_logger(), "Publishing: [%.1f, %.1f, %.1f]", message.data[0], message.data[1], message.data[2]);
    publisher_->publish(message);
}

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<SensorPublisher>();

    // ✅ `public` 메서드를 호출하여 퍼블리시 주기 변경
    node->set_publish_rate(2.0);  

    rclcpp::spin(node);
    rclcpp::shutdown();
    return 0;
}
```
---

# **✅ 3) 코드 구조 분석**
위 코드를 기준으로 **`public`과 `private` 영역을 어떻게 설계하는 것이 좋은지 정리한다.**

| **영역** | **설명** | **코드 예제** |
|---|---|---|
| **`public` 생성자** | 노드의 기본 설정 및 ROS2 객체 초기화 | `SensorPublisher();` |
| **`public` 메서드** | 외부에서 호출 가능한 기능 제공 | `void set_publish_rate(double rate);` |
| **`private` 메서드** | 노드 내부에서만 실행되는 기능 | `void publish_data();` |
| **`private` 멤버 변수** | 퍼블리셔, 타이머, 설정 값 등 | `rclcpp::Publisher<> publisher_;` |

---

# **✅ 4) `public`과 `private` 설계 원칙**
### **📌 1) `public`에는 외부에서 접근 가능한 인터페이스만 포함**
- **노드를 초기화하는 생성자**
- **외부에서 설정을 변경할 수 있는 함수**
- **노드를 실행하는 메서드(`run()`, `start()`, `stop()` 등, 필요할 경우)**

```cpp
class MyNode : public rclcpp::Node {
public:
    MyNode();
    void set_parameter(int value);
};
```
📌 **외부에서 `set_parameter()`를 호출하여 노드 설정을 변경할 수 있음.**

---

### **📌 2) `private`에는 노드 내부에서만 동작하는 기능 포함**
- **퍼블리셔, 서브스크라이버, 서비스, 타이머**
- **콜백 함수(`publish_data()`, `process_data()` 등)**
- **외부에서 직접 접근할 필요가 없는 내부 설정 변수**

```cpp
class MyNode : public rclcpp::Node {
private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};
```
📌 **퍼블리셔와 타이머는 내부적으로만 사용되므로 `private`으로 설정.**

---

### **📌 3) `private` 멤버 변수는 `_`(언더스코어)로 명명**
- **ROS2 코드 스타일 가이드에 따르면, `private` 멤버 변수는 `_`을 붙이는 것이 일반적**  
- `publisher_`, `timer_`, `publish_rate_` 처럼 `_`을 붙여 `public` 변수와 구분  

```cpp
class MyNode : public rclcpp::Node {
private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
    double publish_rate_;
};
```
📌 **이렇게 하면 `public` 변수와 `private` 변수를 쉽게 구분할 수 있음.**

---

# **✅ 5) `public`과 `private`의 최적 구조**
## **📌 권장되는 ROS2 클래스 구조**
```cpp
class MyNode : public rclcpp::Node {
public:
    MyNode();
    void set_publish_rate(double rate);  // ✅ `public` 메서드 (설정 변경)

private:
    void publish_data();  // ✅ `private` 메서드 (콜백)
    
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;  // ✅ `private` 멤버 변수
    rclcpp::TimerBase::SharedPtr timer_;
    double publish_rate_;
};
```
📌 **이 구조를 따르면, 코드가 깔끔해지고 유지보수하기 쉬워진다.**

---

# **📌 정리**
✅ **`public` 영역**에는 **외부에서 접근 가능한 생성자, 설정 변경 메서드**가 포함된다.  
✅ **`private` 영역**에는 **퍼블리셔, 서브스크라이버, 서비스, 타이머, 콜백 함수**가 포함된다.  
✅ **OOP 원칙을 준수하여 캡슐화를 통해 코드의 안정성을 높일 수 있다.**  
✅ **ROS2에서는 `private` 변수의 이름에 `_`(언더스코어)를 붙이는 것이 일반적이다.**  

📌 **이제 `public`과 `private`을 활용하여 깔끔하고 유지보수하기 좋은 ROS2 코드를 작성할 수 있다!** 🚀


<br>
<br>
<br>
<br>
<br>

# **🔹 3-1. C++ 컨테이너 (배열, 벡터, 리스트)**
> **목표:**  
> - C++ STL(Standard Template Library)의 주요 컨테이너(`std::vector`, `std::array`, `std::list`)를 이해하고 ROS2에서 활용하는 방법을 학습한다.  
> - Python의 리스트(`list`)와 C++ 컨테이너의 차이점을 비교하여 효율적인 활용법을 익힌다.  

---

## **✅ C++의 컨테이너와 Python 리스트 비교**
Python에서는 데이터를 저장할 때 **리스트(`list`)**를 사용하지만, C++에서는 **STL 컨테이너**를 사용해야 한다.  
C++의 컨테이너는 데이터의 구조와 성능에 따라 다양한 형태를 제공한다.

| **컨테이너 유형** | **Python** | **C++ STL** | **특징** |
|---|---|---|---|
| **동적 배열** | `list` | `std::vector` | 가변 크기, 빠른 랜덤 접근 |
| **고정 크기 배열** | `tuple` | `std::array` | 크기 고정, 빠른 접근 |
| **연결 리스트** | `collections.deque` | `std::list` | 삽입/삭제 속도 빠름 |

---

## **✅ `std::vector` (동적 배열, Python 리스트와 유사)**
> **`std::vector`는 크기가 동적으로 변경되는 배열이며, Python의 `list`와 가장 유사한 컨테이너이다.**  
> 내부적으로 **동적 메모리 할당을 사용**하며, **배열보다 삽입/삭제가 용이**하다.

---

### **📌 `std::vector` 기본 사용법**
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // 요소 추가
    numbers.push_back(6);  // 리스트 끝에 6 추가

    // 요소 접근
    std::cout << "첫 번째 요소: " << numbers[0] << std::endl;  // 1 출력

    // 크기 확인
    std::cout << "리스트 크기: " << numbers.size() << std::endl;  // 6 출력

    // 요소 삭제
    numbers.pop_back();  // 마지막 요소 삭제

    return 0;
}
```
**📌 실행 결과**
```
첫 번째 요소: 1
리스트 크기: 6
```

---

### **📌 Python 리스트와 비교**
```python
numbers = [1, 2, 3, 4, 5]

# 요소 추가
numbers.append(6)  # 리스트 끝에 6 추가

# 요소 접근
print("첫 번째 요소:", numbers[0])  # 1 출력

# 크기 확인
print("리스트 크기:", len(numbers))  # 6 출력

# 요소 삭제
numbers.pop()  # 마지막 요소 삭제
```
📌 `std::vector`는 **Python 리스트와 거의 동일한 기능을 제공**하지만, **고정된 타입(int, double 등)만 저장 가능**하다.

---

### **📌 `std::vector`의 반복문 활용**
```cpp
std::vector<int> vec = {1, 2, 3, 4, 5};

// ✅ 범위 기반 for 문 (Python과 유사)
for (int num : vec) {
    std::cout << num << " ";
}

// ✅ 일반 for 문 (인덱스 접근)
for (size_t i = 0; i < vec.size(); i++) {
    std::cout << vec[i] << " ";
}
```
📌 **Python과 비슷하게 `for x in list:` 형태로 사용 가능하다.**

---

## **✅ `std::array` (고정 크기 배열)**
> **`std::array`는 크기가 고정된 배열이며, Python의 `tuple`과 유사하다.**  
> **배열의 크기가 변하지 않는 경우, `std::vector`보다 더 빠르게 동작**한다.

---

### **📌 `std::array` 기본 사용법**
```cpp
#include <iostream>
#include <array>

int main() {
    std::array<int, 5> numbers = {1, 2, 3, 4, 5};

    std::cout << "첫 번째 요소: " << numbers[0] << std::endl;
    std::cout << "배열 크기: " << numbers.size() << std::endl;

    return 0;
}
```
📌 `std::array`는 **크기가 고정되어 있어 동적 할당이 필요 없는 경우**에 적합하다.

---

### **📌 Python `tuple`과 비교**
```python
numbers = (1, 2, 3, 4, 5)

print("첫 번째 요소:", numbers[0])
print("배열 크기:", len(numbers))
```
📌 **Python `tuple`과 비슷하지만, C++에서는 크기를 변경할 수 없다.**

---

## **✅ `std::list` (연결 리스트)**
> **`std::list`는 양방향 연결 리스트이며, Python의 `collections.deque`와 유사하다.**  
> **삽입/삭제가 빠르지만, 랜덤 접근 속도가 느리다.**

---

### **📌 `std::list` 기본 사용법**
```cpp
#include <iostream>
#include <list>

int main() {
    std::list<int> numbers = {1, 2, 3, 4, 5};

    // 앞에 추가
    numbers.push_front(0);
    
    // 뒤에 추가
    numbers.push_back(6);

    // 요소 삭제
    numbers.pop_front();  // 첫 번째 요소 삭제

    // 리스트 출력
    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```
📌 `std::list`는 **중간 삽입/삭제가 많을 때 유리**하지만, **랜덤 접근이 필요하면 `std::vector`를 사용하는 것이 좋다.**

---

### **📌 Python `deque`와 비교**
```python
from collections import deque

numbers = deque([1, 2, 3, 4, 5])

# 앞에 추가
numbers.appendleft(0)

# 뒤에 추가
numbers.append(6)

# 첫 번째 요소 삭제
numbers.popleft()

print(list(numbers))  # [1, 2, 3, 4, 5, 6] 출력
```
📌 **Python의 `collections.deque`와 `std::list`는 삽입/삭제에 특화된 구조이다.**

---

## **✅ ROS2에서 STL 컨테이너 활용**
ROS2에서는 **센서 데이터, 메시지 저장, 경로 계획 등** 다양한 곳에서 STL 컨테이너를 활용한다.

### **📌 1) `std::vector`를 사용한 ROS2 퍼블리셔**
> **ROS2 메시지(`std_msgs::msg::Float32MultiArray`)에 `std::vector`를 활용하여 데이터를 전송**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/float32_multi_array.hpp"

class SensorPublisher : public rclcpp::Node {
public:
    SensorPublisher() : Node("sensor_publisher") {
        publisher_ = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", 10);
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&SensorPublisher::publish_data, this)
        );
    }

private:
    void publish_data() {
        auto message = std_msgs::msg::Float32MultiArray();
        message.data = {1.1, 2.2, 3.3};  // ✅ `std::vector`를 사용하여 데이터 저장
        RCLCPP_INFO(this->get_logger(), "Publishing: [%.1f, %.1f, %.1f]", message.data[0], message.data[1], message.data[2]);
        publisher_->publish(message);
    }

    rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<SensorPublisher>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서는 `std::vector`를 메시지 데이터 저장에 자주 활용한다.**

---

# **📌 정리**
✅ **Python `list`는 C++의 `std::vector`와 가장 유사하다.**  
✅ **`std::vector`는 동적 크기 조정이 가능하고, 가장 많이 사용되는 컨테이너이다.**  
✅ **`std::array`는 고정 크기 배열이며, 속도가 빠르다.**  
✅ **`std::list`는 연결 리스트이며, 중간 삽입/삭제가 많을 때 유리하다.**  
✅ **ROS2에서는 `std::vector`를 센서 데이터 저장, 메시지 처리 등 다양한 곳에서 활용한다.** 🚀


<br>
<br>
<br>
<br>

# **🔹 3-2. C++ 맵과 해시맵 (`std::map`, `std::unordered_map`)**
> **목표:**  
> - **C++ STL의 `std::map`과 `std::unordered_map`의 차이를 이해하고, Python의 `dict`와 비교**한다.  
> - **ROS2에서 메시지 데이터를 키-값 형태로 저장하는 활용 사례를 익힌다.**

---

## **✅ Python의 `dict` vs. C++의 `std::map` & `std::unordered_map`**
Python에서는 **키-값(key-value) 데이터 구조**를 저장할 때 `dict`(딕셔너리)를 사용한다.  
C++에서는 **비슷한 역할을 하는 컨테이너**로 `std::map`(정렬된 맵)과 `std::unordered_map`(해시맵)이 있다.

| **컨테이너 유형** | **Python** | **C++ STL** | **특징** |
|---|---|---|---|
| **정렬된 맵** | `dict` (3.7+에서 입력 순서 유지) | `std::map` | **키가 자동 정렬됨** (이진 검색 트리, O(log n)) |
| **해시맵** | `dict` (해시 기반) | `std::unordered_map` | **해시 기반 빠른 검색** (평균 O(1), 최악 O(n)) |

📌 **Python 3.7 이상부터 `dict`는 입력 순서를 유지하지만, C++ `std::map`은 자동 정렬된다.**  
📌 **Python `dict`는 내부적으로 해시 테이블을 사용하므로 `std::unordered_map`과 유사하다.**

---

## **✅ `std::map` (자동 정렬되는 키-값 컨테이너)**
> **`std::map`은 키를 자동으로 정렬하며, 내부적으로 이진 검색 트리(Red-Black Tree)를 사용한다.**  
> - **시간 복잡도:** 검색/삽입/삭제 → `O(log n)`  
> - **장점:** 키가 정렬된 상태로 유지됨  
> - **단점:** `std::unordered_map`보다 검색 속도가 느림  

---

### **📌 `std::map` 기본 사용법**
```cpp
#include <iostream>
#include <map>

int main() {
    std::map<std::string, int> robot_speeds;

    // ✅ 데이터 삽입 (자동 정렬됨)
    robot_speeds["TurtleBot"] = 2;
    robot_speeds["Spot"] = 5;
    robot_speeds["Atlas"] = 10;

    // ✅ 요소 접근
    std::cout << "TurtleBot 속도: " << robot_speeds["TurtleBot"] << " m/s" << std::endl;

    // ✅ 반복문을 통한 모든 요소 출력 (자동 정렬됨)
    for (const auto &pair : robot_speeds) {
        std::cout << pair.first << " → " << pair.second << " m/s" << std::endl;
    }

    return 0;
}
```
**📌 실행 결과 (자동 정렬)**
```
TurtleBot 속도: 2 m/s
Atlas → 10 m/s
Spot → 5 m/s
TurtleBot → 2 m/s
```
📌 **`std::map`은 키를 자동 정렬하며, 검색/삽입 속도가 `O(log n)`이다.**

---

### **📌 Python `dict`와 비교**
```python
robot_speeds = {
    "TurtleBot": 2,
    "Spot": 5,
    "Atlas": 10
}

# 요소 접근
print("TurtleBot 속도:", robot_speeds["TurtleBot"], "m/s")

# 모든 요소 출력 (Python 3.7 이상에서는 입력 순서 유지)
for key, value in robot_speeds.items():
    print(f"{key} → {value} m/s")
```
📌 **Python `dict`는 C++ `std::unordered_map`과 비슷한 속성(해시 기반)을 가진다.**

---

## **✅ `std::unordered_map` (해시맵, 빠른 검색)**
> **`std::unordered_map`은 내부적으로 해시 테이블을 사용하여 빠른 검색을 제공한다.**  
> - **시간 복잡도:** 평균 `O(1)`, 최악 `O(n)`  
> - **장점:** 검색 속도가 `std::map`보다 빠름  
> - **단점:** 키가 정렬되지 않음  

---

### **📌 `std::unordered_map` 기본 사용법**
```cpp
#include <iostream>
#include <unordered_map>

int main() {
    std::unordered_map<std::string, int> robot_speeds;

    // ✅ 데이터 삽입 (순서가 유지되지 않음)
    robot_speeds["TurtleBot"] = 2;
    robot_speeds["Spot"] = 5;
    robot_speeds["Atlas"] = 10;

    // ✅ 요소 접근
    std::cout << "Spot 속도: " << robot_speeds["Spot"] << " m/s" << std::endl;

    // ✅ 반복문을 통한 출력 (입력 순서가 유지되지 않음)
    for (const auto &pair : robot_speeds) {
        std::cout << pair.first << " → " << pair.second << " m/s" << std::endl;
    }

    return 0;
}
```
**📌 실행 결과 (순서가 일정하지 않음)**
```
Spot 속도: 5 m/s
TurtleBot → 2 m/s
Spot → 5 m/s
Atlas → 10 m/s
```
📌 **`std::unordered_map`은 검색이 `O(1)`로 매우 빠르지만, 키 순서가 유지되지 않는다.**

---

## **✅ ROS2에서 `std::map`과 `std::unordered_map` 활용**
ROS2에서는 **토픽과 노드를 동적으로 매핑하거나, 메시지 데이터를 키-값 형태로 저장할 때 `std::map`을 활용**할 수 있다.

---

### **📌 1) ROS2에서 `std::map`을 활용한 로봇 ID-좌표 매핑**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <map>

class RobotManager : public rclcpp::Node {
public:
    RobotManager() : Node("robot_manager") {
        // ✅ 로봇 ID와 좌표 매핑
        robot_positions_["TurtleBot"] = {1.0, 2.0};
        robot_positions_["Spot"] = {3.5, 4.2};
        robot_positions_["Atlas"] = {5.0, 6.1};

        print_positions();
    }

private:
    struct Position {
        double x, y;
    };
    
    std::map<std::string, Position> robot_positions_;

    void print_positions() {
        for (const auto &pair : robot_positions_) {
            RCLCPP_INFO(this->get_logger(), "%s 위치: (%.1f, %.1f)", 
                        pair.first.c_str(), pair.second.x, pair.second.y);
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<RobotManager>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서 `std::map`을 사용하여 로봇 ID와 좌표를 효율적으로 관리할 수 있다.**

---

### **📌 2) `std::unordered_map`을 사용한 ROS2 노드 핸들 저장**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <unordered_map>

class NodeManager : public rclcpp::Node {
public:
    NodeManager() : Node("node_manager") {
        // ✅ 노드 이름과 공유 포인터 매핑
        node_registry_["sensor_node"] = this->create_sub_node("sensor_node");
        node_registry_["controller_node"] = this->create_sub_node("controller_node");

        print_nodes();
    }

private:
    std::unordered_map<std::string, std::shared_ptr<rclcpp::Node>> node_registry_;

    void print_nodes() {
        for (const auto &pair : node_registry_) {
            RCLCPP_INFO(this->get_logger(), "노드 등록: %s", pair.first.c_str());
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<NodeManager>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서 `std::unordered_map`을 활용하면 노드 핸들을 빠르게 검색할 수 있다.**

---

# **📌 정리**
✅ **Python `dict`는 `std::unordered_map`과 유사하며, `std::map`은 자동 정렬된 `dict`와 유사하다.**  
✅ **`std::map`은 키 정렬이 필요할 때, `std::unordered_map`은 빠른 검색이 필요할 때 사용한다.**  
✅ **ROS2에서는 `std::map`을 로봇 ID-좌표 매핑, `std::unordered_map`을 빠른 노드 검색 등에 활용할 수 있다.** 🚀


<br>
<br>
<br>
<br>

# **🔹 `std::unordered_map`을 활용한 ROS2 노드 핸들 저장 (쉽게 이해하기)**
> **목표:**  
> - `std::unordered_map`을 활용하여 **ROS2 노드의 핸들(Node Handle)을 저장하는 방법을 익힌다.**  
> - 코드가 이해하기 어렵다면, **하나씩 차근차근 분석하면서 설명**한다.  
> - `std::unordered_map`을 활용하면 **동적으로 생성된 여러 개의 노드를 빠르게 검색하고 관리**할 수 있다.  

---

## **✅ `std::unordered_map`이 필요한 이유**
### **🛑 문제: 여러 개의 ROS2 노드를 효율적으로 관리하려면?**
- ROS2에서는 하나의 실행 파일에서 여러 개의 노드를 생성할 수 있다.
- **여러 개의 노드를 저장하고, 필요할 때 빠르게 검색하려면?**
- **해결 방법:** `std::unordered_map`을 활용하여 **"노드 이름" ↔ "노드 객체"** 를 연결한다.

📌 `std::unordered_map<std::string, std::shared_ptr<rclcpp::Node>>`  
➡ **문자열(노드 이름)을 키(key)로, 노드 객체를 값(value)로 저장**한다.

---

## **✅ 코드 분석 (기본적인 ROS2 노드 핸들 저장)**
아래 코드를 하나씩 분석하면서 설명하겠다.

```cpp
#include "rclcpp/rclcpp.hpp"
#include <unordered_map>

class NodeManager : public rclcpp::Node {
public:
    NodeManager() : Node("node_manager") {
        // ✅ 여러 개의 노드를 생성하여 맵에 저장
        node_registry_["sensor_node"] = std::make_shared<rclcpp::Node>("sensor_node");
        node_registry_["controller_node"] = std::make_shared<rclcpp::Node>("controller_node");

        print_nodes();
    }

private:
    // ✅ 노드 이름(string) → 노드 객체(std::shared_ptr<rclcpp::Node>) 매핑
    std::unordered_map<std::string, std::shared_ptr<rclcpp::Node>> node_registry_;

    void print_nodes() {
        for (const auto &pair : node_registry_) {
            RCLCPP_INFO(this->get_logger(), "노드 등록됨: %s", pair.first.c_str());
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<NodeManager>());
    rclcpp::shutdown();
    return 0;
}
```

---

## **✅ 코드 세부 설명**
### **📌 1) `std::unordered_map` 선언**
```cpp
std::unordered_map<std::string, std::shared_ptr<rclcpp::Node>> node_registry_;
```
📌 **의미:**  
- **키(key):** `std::string` → 노드 이름 (예: `"sensor_node"`, `"controller_node"`)  
- **값(value):** `std::shared_ptr<rclcpp::Node>` → 해당 노드의 스마트 포인터  

**➡ 이 맵을 활용하면 문자열(노드 이름)로 노드 객체를 빠르게 찾을 수 있다!**  

---

### **📌 2) 여러 개의 노드를 동적으로 생성하여 저장**
```cpp
node_registry_["sensor_node"] = std::make_shared<rclcpp::Node>("sensor_node");
node_registry_["controller_node"] = std::make_shared<rclcpp::Node>("controller_node");
```
📌 **의미:**  
- `"sensor_node"` 키에 해당하는 새로운 ROS2 노드를 생성하고 `std::shared_ptr`로 저장한다.
- `"controller_node"` 키에도 동일한 방식으로 노드를 저장한다.
- **맵(`node_registry_`)에 저장된 노드는 프로그램이 실행되는 동안 계속 유지된다.**

**➡ 맵을 활용하여 여러 개의 노드를 효율적으로 관리할 수 있다!**

---

### **📌 3) 등록된 노드 목록 출력**
```cpp
void print_nodes() {
    for (const auto &pair : node_registry_) {
        RCLCPP_INFO(this->get_logger(), "노드 등록됨: %s", pair.first.c_str());
    }
}
```
📌 **의미:**  
- `for (const auto &pair : node_registry_)`  
  **맵의 모든 요소를 반복하면서 출력** (`pair.first` = 키(노드 이름), `pair.second` = 노드 객체)
- `RCLCPP_INFO(this->get_logger(), "노드 등록됨: %s", pair.first.c_str());`  
  → **ROS2 로그(INFO)로 노드 이름 출력**

**➡ 실행하면 저장된 노드 목록이 출력된다!**

---

## **✅ 코드 실행 결과**
```
[INFO] [node_manager]: 노드 등록됨: sensor_node
[INFO] [node_manager]: 노드 등록됨: controller_node
```
📌 **맵(`std::unordered_map`)을 활용하여 여러 개의 노드를 효과적으로 관리하고 있음을 확인할 수 있다!** 🚀

---

## **✅ 추가 예제: 특정 노드 검색하기**
맵을 활용하면 특정 노드를 검색할 수도 있다.

### **📌 노드 검색 기능 추가**
```cpp
void find_node(const std::string &node_name) {
    auto it = node_registry_.find(node_name);
    if (it != node_registry_.end()) {
        RCLCPP_INFO(this->get_logger(), "노드 찾음: %s", node_name.c_str());
    } else {
        RCLCPP_WARN(this->get_logger(), "노드 없음: %s", node_name.c_str());
    }
}
```
📌 **의미:**  
- `node_registry_.find(node_name)` → **노드가 존재하는지 확인**  
- **찾으면:** `"노드 찾음: <이름>"` 출력  
- **없으면:** `"노드 없음: <이름>"` 경고 출력  

### **📌 `find_node()` 호출 추가**
```cpp
find_node("sensor_node");   // ✅ 존재하는 노드 검색
find_node("unknown_node");  // ❌ 존재하지 않는 노드 검색
```

---

### **📌 실행 결과**
```
[INFO] [node_manager]: 노드 등록됨: sensor_node
[INFO] [node_manager]: 노드 등록됨: controller_node
[INFO] [node_manager]: 노드 찾음: sensor_node
[WARN] [node_manager]: 노드 없음: unknown_node
```
📌 **맵을 활용하면 특정 노드가 존재하는지 쉽게 확인할 수 있다!** 🎯

---

## **✅ `std::unordered_map` vs. `std::map` 비교**
| **특징** | **std::map (정렬됨)** | **std::unordered_map (해시맵)** |
|---|---|---|
| **정렬 여부** | 키가 자동 정렬됨 | 키의 순서가 유지되지 않음 |
| **탐색 속도** | `O(log n)` (이진 탐색 트리) | `O(1)` (평균) |
| **삽입/삭제 속도** | 느림 (`O(log n)`) | 빠름 (`O(1)`, 최악 `O(n)`) |
| **추천 사용 사례** | **정렬이 필요할 때 (예: 로봇 ID 순서 정렬)** | **빠른 검색이 필요할 때 (예: ROS2 노드 핸들 저장)** |

📌 **ROS2에서 빠르게 노드를 찾으려면 `std::unordered_map`이 유리하다.**  
📌 **반대로, 특정 순서대로 노드를 정렬해야 하면 `std::map`을 사용해야 한다.**

---

# **📌 정리**
✅ **여러 개의 ROS2 노드를 저장하고 관리하기 위해 `std::unordered_map`을 활용할 수 있다.**  
✅ **"노드 이름" → "노드 객체" 형태로 맵핑하여, 특정 노드를 빠르게 검색할 수 있다.**  
✅ **맵을 활용하면 노드를 추가, 삭제, 검색할 수 있어 더욱 동적인 ROS2 시스템을 만들 수 있다.**  
✅ **빠른 검색이 필요하면 `std::unordered_map`, 정렬이 필요하면 `std::map`을 사용하면 된다.**  

📌 이제 `std::unordered_map`을 활용하여 **다양한 ROS2 애플리케이션을 설계**할 수 있다! 🚀



<br>
<br>
<br>
<br>

# **🔹 `std::unordered_map`을 활용한 ROS2 노드 핸들 매니저 활용 사례**
> **목표:**  
> - **ROS2에서 `std::unordered_map`을 활용한 노드 핸들 매니저가 필요한 상황을 구체적으로 이해한다.**  
> - **Python에서 동일한 기능을 구현한 코드와 비교하여 차이점을 명확히 이해한다.**  

---

## **✅ `std::unordered_map` 기반 ROS2 노드 핸들 매니저가 필요한 상황**
**🤖 시나리오:**  
- 여러 개의 로봇이 **동적으로 추가되거나 삭제되는 상황**에서 각 로봇을 제어하는 ROS2 노드들이 존재한다고 가정하자.  
- 모든 로봇의 노드를 실행하면서, 특정 로봇 노드를 **검색, 추가, 삭제**할 수 있어야 한다.  
- **요구사항:**
  - 동적으로 **새로운 로봇을 등록하거나 삭제**할 수 있어야 함.
  - 특정 로봇의 **노드 정보를 빠르게 검색**할 수 있어야 함.
  - 특정 노드가 존재하는지 **O(1)** 시간 안에 확인할 수 있어야 함.

➡ **해결 방법:**  
✅ **"로봇 이름"을 키(`std::string`)로 사용하고, "로봇의 ROS2 노드 핸들"을 값(`std::shared_ptr<rclcpp::Node>`)으로 저장하는 `std::unordered_map`을 활용한다.**  
✅ **검색이 빠르고(`O(1)`), 삽입/삭제가 유연하므로, 로봇 수가 증가해도 효율적으로 관리할 수 있다.**

---

## **✅ `std::unordered_map`을 활용한 ROS2 노드 핸들 매니저 구현**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <unordered_map>

class RobotNodeManager : public rclcpp::Node {
public:
    RobotNodeManager() : Node("robot_node_manager") {
        RCLCPP_INFO(this->get_logger(), "로봇 노드 매니저가 시작되었습니다.");
    }

    // ✅ 로봇 노드 추가 (동적으로 등록)
    void add_robot(const std::string &robot_name) {
        if (robot_registry_.find(robot_name) == robot_registry_.end()) {
            robot_registry_[robot_name] = std::make_shared<rclcpp::Node>(robot_name);
            RCLCPP_INFO(this->get_logger(), "로봇 '%s'이(가) 등록되었습니다.", robot_name.c_str());
        } else {
            RCLCPP_WARN(this->get_logger(), "로봇 '%s'은(는) 이미 등록되어 있습니다.", robot_name.c_str());
        }
    }

    // ✅ 특정 로봇 노드 검색 (O(1) 시간 복잡도)
    bool find_robot(const std::string &robot_name) {
        if (robot_registry_.find(robot_name) != robot_registry_.end()) {
            RCLCPP_INFO(this->get_logger(), "로봇 '%s'을(를) 찾았습니다.", robot_name.c_str());
            return true;
        } else {
            RCLCPP_WARN(this->get_logger(), "로봇 '%s'을(를) 찾을 수 없습니다.", robot_name.c_str());
            return false;
        }
    }

    // ✅ 로봇 노드 삭제 (동적으로 제거)
    void remove_robot(const std::string &robot_name) {
        if (robot_registry_.erase(robot_name)) {
            RCLCPP_INFO(this->get_logger(), "로봇 '%s'이(가) 제거되었습니다.", robot_name.c_str());
        } else {
            RCLCPP_WARN(this->get_logger(), "로봇 '%s'이(가) 존재하지 않아 제거할 수 없습니다.", robot_name.c_str());
        }
    }

private:
    std::unordered_map<std::string, std::shared_ptr<rclcpp::Node>> robot_registry_;  // 로봇 이름 -> 노드 매핑
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto manager = std::make_shared<RobotNodeManager>();

    // ✅ 로봇 노드 추가
    manager->add_robot("TurtleBot");
    manager->add_robot("Spot");

    // ✅ 특정 로봇 검색
    manager->find_robot("TurtleBot");
    manager->find_robot("UnknownBot");

    // ✅ 로봇 노드 삭제
    manager->remove_robot("Spot");
    manager->remove_robot("UnknownBot");

    rclcpp::shutdown();
    return 0;
}
```

---

### **📌 실행 결과**
```
[INFO] [robot_node_manager]: 로봇 노드 매니저가 시작되었습니다.
[INFO] [robot_node_manager]: 로봇 'TurtleBot'이(가) 등록되었습니다.
[INFO] [robot_node_manager]: 로봇 'Spot'이(가) 등록되었습니다.
[INFO] [robot_node_manager]: 로봇 'TurtleBot'을(를) 찾았습니다.
[WARN] [robot_node_manager]: 로봇 'UnknownBot'을(를) 찾을 수 없습니다.
[INFO] [robot_node_manager]: 로봇 'Spot'이(가) 제거되었습니다.
[WARN] [robot_node_manager]: 로봇 'UnknownBot'이(가) 존재하지 않아 제거할 수 없습니다.
```
📌 **동적으로 로봇을 추가하고 검색/삭제할 수 있으며, 존재 여부를 빠르게 확인할 수 있다.** 🚀

---

## **✅ 동일한 기능을 Python 코드로 구현**
**Python에서도 같은 기능을 `dict`(해시맵 기반)로 쉽게 구현할 수 있다.**
```python
import rclpy
from rclpy.node import Node

class RobotNodeManager(Node):
    def __init__(self):
        super().__init__("robot_node_manager")
        self.get_logger().info("로봇 노드 매니저가 시작되었습니다.")
        self.robot_registry = {}  # Python의 `dict` 사용

    # ✅ 로봇 노드 추가
    def add_robot(self, robot_name):
        if robot_name not in self.robot_registry:
            self.robot_registry[robot_name] = Node(robot_name)
            self.get_logger().info(f"로봇 '{robot_name}'이(가) 등록되었습니다.")
        else:
            self.get_logger().warn(f"로봇 '{robot_name}'은(는) 이미 등록되어 있습니다.")

    # ✅ 특정 로봇 노드 검색
    def find_robot(self, robot_name):
        if robot_name in self.robot_registry:
            self.get_logger().info(f"로봇 '{robot_name}'을(를) 찾았습니다.")
            return True
        else:
            self.get_logger().warn(f"로봇 '{robot_name}'을(를) 찾을 수 없습니다.")
            return False

    # ✅ 로봇 노드 삭제
    def remove_robot(self, robot_name):
        if robot_name in self.robot_registry:
            del self.robot_registry[robot_name]
            self.get_logger().info(f"로봇 '{robot_name}'이(가) 제거되었습니다.")
        else:
            self.get_logger().warn(f"로봇 '{robot_name}'이(가) 존재하지 않아 제거할 수 없습니다.")

def main(args=None):
    rclpy.init(args=args)
    manager = RobotNodeManager()

    # ✅ 로봇 노드 추가
    manager.add_robot("TurtleBot")
    manager.add_robot("Spot")

    # ✅ 특정 로봇 검색
    manager.find_robot("TurtleBot")
    manager.find_robot("UnknownBot")

    # ✅ 로봇 노드 삭제
    manager.remove_robot("Spot")
    manager.remove_robot("UnknownBot")

    rclpy.shutdown()

if __name__ == "__main__":
    main()
```

---

## **✅ C++ `std::unordered_map` vs. Python `dict` 비교**
| 기능 | C++ (`std::unordered_map`) | Python (`dict`) |
|---|---|---|
| **기본 구조** | 해시맵 기반 | 해시맵 기반 |
| **삽입 속도** | `O(1)` (평균), `O(n)` (최악) | `O(1)` |
| **검색 속도** | `O(1)` (평균), `O(n)` (최악) | `O(1)` |
| **정렬 여부** | 정렬되지 않음 | Python 3.7+부터 입력 순서 유지 |
| **메모리 관리** | `std::shared_ptr` 필요 | 자동 가비지 컬렉션 |

📌 **Python `dict`는 C++의 `std::unordered_map`과 거의 동일한 성능을 제공하지만, 메모리 관리는 Python이 더 쉽다.**  
📌 **C++에서는 `std::shared_ptr`을 사용하여 객체의 수명을 안전하게 관리해야 한다.**

---

# **📌 정리**
✅ **여러 개의 ROS2 노드를 관리할 때 `std::unordered_map`을 활용하면 빠른 검색이 가능하다.**  
✅ **C++에서는 `std::shared_ptr`을 사용하여 노드 객체의 메모리를 안전하게 관리해야 한다.**  
✅ **Python에서는 `dict`를 사용하여 동일한 기능을 간단하게 구현할 수 있다.**  
✅ **빠른 노드 검색이 필요한 경우, `std::unordered_map`을 활용하면 최적의 성능을 제공한다.** 🚀


<br>
<br>
<br>
<br>

# **🔹 3-3. C++ 알고리즘 라이브러리 (`<algorithm>`)**
> **목표:**  
> - C++ 표준 라이브러리(STL)의 `std::sort()`, `std::find()`, `std::transform()`의 사용법을 익힌다.  
> - Python의 `sorted()` 및 기타 함수와 비교하여 차이점을 이해한다.  
> - **ROS2에서 센서 데이터 정렬, 특정 값 찾기, 데이터 변환 등의 활용 사례**를 익힌다.  

---

## **✅ C++ `<algorithm>` 라이브러리란?**
C++ `<algorithm>`은 **데이터를 정렬, 검색, 변환하는 유용한 함수들을 포함한 표준 라이브러리**이다.  
Python에서는 `sorted()`, `map()`, `filter()`, `list.index()` 같은 기능이 있지만, C++에서는 `<algorithm>`을 사용하여 비슷한 기능을 제공한다.  

---

# **🔹 `std::sort()` – 정렬하기**
> **`std::sort()`는 `O(n log n)`의 시간 복잡도로 배열 또는 컨테이너를 빠르게 정렬한다.**  
> - **기본적으로 오름차순 정렬을 수행하며, 비교 함수를 제공하면 내림차순 또는 사용자 정의 정렬이 가능하다.**  
> - Python의 `sorted()`와 유사하다.

---

### **📌 `std::sort()` 기본 사용법 (오름차순 정렬)**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>  // ✅ `std::sort` 포함

int main() {
    std::vector<int> numbers = {5, 3, 8, 1, 2};

    std::sort(numbers.begin(), numbers.end());  // ✅ 오름차순 정렬

    std::cout << "정렬된 숫자: ";
    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```
**📌 실행 결과**
```
정렬된 숫자: 1 2 3 5 8
```
📌 **Python의 `sorted(numbers)`와 같은 기능을 한다.**

---

### **📌 `std::sort()` 내림차순 정렬**
Python에서 `sorted(numbers, reverse=True)`를 하는 것과 같은 기능이다.

```cpp
std::sort(numbers.begin(), numbers.end(), std::greater<int>());
```

### **📌 `std::sort()` 비교 함수 활용**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

// ✅ 사용자 정의 비교 함수 (짝수를 먼저 정렬)
bool customCompare(int a, int b) {
    return (a % 2 == 0) && (b % 2 != 0);
}

int main() {
    std::vector<int> numbers = {5, 3, 8, 1, 2};

    std::sort(numbers.begin(), numbers.end(), customCompare);

    std::cout << "짝수 먼저 정렬: ";
    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
```
**📌 실행 결과**
```
짝수 먼저 정렬: 8 2 5 3 1
```
📌 **짝수를 우선적으로 정렬하는 방식으로 변경했다.**  
📌 **Python에서는 `sorted(numbers, key=lambda x: (x % 2, x))` 와 유사한 기능을 한다.**

---

### **📌 Python `sorted()`와 비교**
```python
numbers = [5, 3, 8, 1, 2]

# 기본 정렬 (오름차순)
print(sorted(numbers))  # [1, 2, 3, 5, 8]

# 내림차순 정렬
print(sorted(numbers, reverse=True))  # [8, 5, 3, 2, 1]

# 사용자 정의 정렬 (짝수 먼저)
print(sorted(numbers, key=lambda x: (x % 2, x)))  # [2, 8, 1, 3, 5]
```
📌 **Python과 매우 유사하지만, C++에서는 `std::greater<int>()` 또는 사용자 정의 함수로 구현해야 한다.**

---

# **🔹 `std::find()` – 특정 값 찾기**
> **`std::find()`는 컨테이너에서 특정 값을 검색하는 함수이다.**  
> - Python의 `list.index(value)` 또는 `if value in list:` 문법과 유사하다.  
> - 시간 복잡도는 `O(n)`이며, **값을 찾으면 반복자(iterator)를 반환**한다.

---

### **📌 `std::find()` 기본 사용법**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>  // ✅ `std::find` 포함

int main() {
    std::vector<int> numbers = {10, 20, 30, 40, 50};
    
    int target = 30;
    auto it = std::find(numbers.begin(), numbers.end(), target);  // ✅ 값 찾기

    if (it != numbers.end()) {
        std::cout << "값을 찾았습니다: " << *it << std::endl;
    } else {
        std::cout << "값을 찾을 수 없습니다." << std::endl;
    }

    return 0;
}
```
**📌 실행 결과**
```
값을 찾았습니다: 30
```
📌 **Python의 `if 30 in numbers:` 또는 `numbers.index(30)`와 유사하다.**

---

### **📌 Python에서 `std::find()`와 동일한 기능**
```python
numbers = [10, 20, 30, 40, 50]

# 값 찾기
target = 30
if target in numbers:
    print("값을 찾았습니다:", target)
else:
    print("값을 찾을 수 없습니다.")
```

📌 **C++은 반복자를 반환하고, Python은 `in` 연산자를 사용하여 더 직관적으로 표현할 수 있다.**

---

# **🔹 `std::transform()` – 데이터 변환**
> **`std::transform()`은 컨테이너의 요소를 변환하는 함수이다.**  
> - Python의 `map()`과 유사하다.  
> - **각 요소에 특정 함수를 적용한 새로운 컨테이너를 생성한다.**

---

### **📌 `std::transform()` 기본 사용법**
```cpp
#include <iostream>
#include <vector>
#include <algorithm>  // ✅ `std::transform` 포함

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::vector<int> squared(numbers.size());

    // ✅ 각 요소를 제곱으로 변환
    std::transform(numbers.begin(), numbers.end(), squared.begin(), [](int x) { return x * x; });

    std::cout << "제곱된 값: ";
    for (int num : squared) {
        std::cout << num << " ";
    }

    return 0;
}
```
**📌 실행 결과**
```
제곱된 값: 1 4 9 16 25
```
📌 **Python의 `map(lambda x: x*x, numbers)` 와 유사하다.**

---

### **📌 Python에서 `std::transform()`과 동일한 기능**
```python
numbers = [1, 2, 3, 4, 5]

# 각 요소를 제곱으로 변환
squared = list(map(lambda x: x*x, numbers))

print("제곱된 값:", squared)  # [1, 4, 9, 16, 25]
```
📌 **Python에서는 `map()`을 사용하며, C++에서는 `std::transform()`을 사용한다.**

---

# **🔹 ROS2에서 `std::sort()`, `std::find()`, `std::transform()` 활용**
## **✅ ROS2에서 센서 데이터를 정렬하고, 특정 값 찾고, 변환하기**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <vector>
#include <algorithm>

class SensorNode : public rclcpp::Node {
public:
    SensorNode() : Node("sensor_node") {
        std::vector<float> sensor_data = {3.2, 1.5, 4.8, 2.1};

        // ✅ 센서 데이터 정렬
        std::sort(sensor_data.begin(), sensor_data.end());

        // ✅ 특정 값 찾기
        auto it = std::find(sensor_data.begin(), sensor_data.end(), 2.1);
        if (it != sensor_data.end()) {
            RCLCPP_INFO(this->get_logger(), "값 2.1 찾음!");
        }

        // ✅ 데이터 변환 (센서 값을 배율 2배 증가)
        std::transform(sensor_data.begin(), sensor_data.end(), sensor_data.begin(), [](float x) { return x * 2; });

        for (float val : sensor_data) {
            RCLCPP_INFO(this->get_logger(), "변환된 값: %.2f", val);
        }
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<SensorNode>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2에서 센서 데이터를 정렬하고, 특정 값을 찾고, 변환하는 데 `std::sort()`, `std::find()`, `std::transform()`을 활용할 수 있다!** 🚀


<br>
<br>
<br>

# **🔹 `*it`에서 `*`(역참조 연산자)의 의미**
> **질문:**  
> `std::find()`로 찾은 값이 `*it`로 출력되는 이유는?  
> `*` 기호가 왜 필요한가?

### **✅ `std::find()`는 "반복자(iterator)"를 반환한다.**
```cpp
auto it = std::find(numbers.begin(), numbers.end(), target);
```
📌 `std::find()`의 반환값은 **반복자(iterator)**이다.  
📌 **반복자는 해당 컨테이너의 요소를 가리키는 "포인터와 유사한 개념"**이다.  

---

## **✅ `*it`를 사용해야 하는 이유**
> **반복자는 직접 값을 반환하지 않는다.**  
> 반복자가 가리키는 실제 값을 얻으려면 `*it`(역참조 연산자)을 사용해야 한다.

### **📌 `std::find()`의 동작 과정**
```cpp
std::vector<int> numbers = {10, 20, 30, 40, 50};

int target = 30;
auto it = std::find(numbers.begin(), numbers.end(), target);  // 반복자 반환
```
- `it`는 `std::vector<int>::iterator` 타입의 변수이다.
- `it`는 **`numbers` 벡터 내에서 `30`이 위치한 곳을 가리키는 반복자**이다.
- `it` 자체는 값이 아니라 **메모리 상의 위치를 가리킨다.**
- 따라서, **실제 값(30)을 출력하려면 `*it`로 역참조해야 한다.**

---

## **✅ `*it` 없이 실행하면 오류 발생**
### **📌 잘못된 코드 (오류 발생)**
```cpp
std::cout << "값을 찾았습니다: " << it << std::endl;  // ❌ 오류 발생
```
📌 `it`는 **반복자(iterator) 자체**이므로, `std::cout`으로 직접 출력할 수 없다.  
📌 **반복자가 가리키는 값을 가져오려면 `*it`을 사용해야 한다.**

---

## **✅ `*it`을 사용한 올바른 코드**
```cpp
if (it != numbers.end()) {
    std::cout << "값을 찾았습니다: " << *it << std::endl;  // ✅ 올바른 사용법
} else {
    std::cout << "값을 찾을 수 없습니다." << std::endl;
}
```
📌 **반복자가 가리키는 값을 출력하기 위해 `*it`을 사용한다.**

---

## **✅ Python에서 `*it`과 같은 개념**
```python
numbers = [10, 20, 30, 40, 50]

# Python에서는 직접 값 반환 가능
target = 30
if target in numbers:
    print("값을 찾았습니다:", target)
else:
    print("값을 찾을 수 없습니다.")
```
📌 Python에서는 `target in numbers`로 바로 값을 찾을 수 있다.  
📌 **C++에서는 `std::find()`가 반복자를 반환하기 때문에, `*it`을 사용해야 한다.**

---

## **✅ 요약**
| **C++ (`std::find`)** | **Python (`in` 연산자)** |
|---|---|
| `std::find()`는 **반복자(iterator)** 반환 | `list.index()` 또는 `in` 연산자는 **값 자체 반환** |
| 값에 접근하려면 `*it`(역참조) 사용 | `target`을 바로 사용 가능 |
| `it` 자체를 출력하면 오류 발생 | Python에서는 별도 역참조 불필요 |

📌 **C++에서 `std::find()`의 결과는 반복자(iterator)이므로, 값을 출력할 때 `*it`(역참조 연산자)을 반드시 사용해야 한다.** 🚀


<br>
<br>
<br>
<br>

# **🔹 4-1. C++의 기본 멀티스레딩 (`std::thread`)**
> **목표:**  
> - C++의 기본 멀티스레딩 기능인 `std::thread`를 이해한다.  
> - Python의 `threading`과 비교하여 차이점을 익힌다.  
> - `std::mutex`를 사용하여 **여러 스레드 간의 데이터 동기화 방법**을 배운다.  
> - ROS2에서 멀티스레딩을 활용하는 방법을 학습한다.  

---

## **✅ Python의 `threading`과 C++ `std::thread` 비교**
Python과 C++에서 멀티스레딩을 구현하는 방식은 다음과 같다.

| **기능** | **Python (`threading`)** | **C++ (`std::thread`)** |
|---|---|---|
| **스레드 생성** | `threading.Thread(target=function)` | `std::thread t(function);` |
| **스레드 실행** | `t.start()` | 생성과 동시에 실행됨 |
| **스레드 종료 대기** | `t.join()` | `t.join();` |
| **데이터 동기화** | `threading.Lock()` | `std::mutex` |
| **병렬성 (GIL 문제)** | GIL로 인해 진정한 병렬 실행 불가능 | 진정한 병렬 실행 가능 |

📌 **Python의 `threading` 모듈은 GIL(Global Interpreter Lock)로 인해 CPU-bound 작업에서 성능 향상이 어렵다.**  
📌 **C++의 `std::thread`는 OS에서 직접 관리하는 스레드를 사용하므로, 진정한 병렬 실행이 가능하다.**  

---

# **🔹 `std::thread` 기본 사용법**
C++에서 **멀티스레드를 사용하려면** `<thread>` 헤더를 포함해야 한다.

---

## **✅ 1) 기본적인 `std::thread` 사용법**
> **여러 개의 스레드를 생성하고 실행하는 기본적인 방법을 배운다.**

```cpp
#include <iostream>
#include <thread>

// ✅ 스레드에서 실행할 함수
void print_message(const std::string &msg) {
    for (int i = 0; i < 5; i++) {
        std::cout << msg << " " << i << std::endl;
    }
}

int main() {
    // ✅ 두 개의 스레드를 실행
    std::thread t1(print_message, "스레드 1");
    std::thread t2(print_message, "스레드 2");

    // ✅ 스레드가 종료될 때까지 대기
    t1.join();
    t2.join();

    std::cout << "모든 스레드 종료!" << std::endl;
    return 0;
}
```
### **📌 실행 결과 (스레드가 병렬로 실행됨)**
```
스레드 1 0
스레드 2 0
스레드 1 1
스레드 2 1
스레드 1 2
스레드 2 2
스레드 1 3
스레드 2 3
스레드 1 4
스레드 2 4
모든 스레드 종료!
```
📌 **출력 순서는 실행할 때마다 다를 수 있다.**  
📌 `std::thread`는 생성과 동시에 실행된다.  
📌 `t1.join();`과 `t2.join();`을 호출해야 메인 스레드가 종료될 때까지 기다린다.  

---

## **✅ 2) Python의 `threading`과 비교**
### **📌 Python에서 동일한 코드**
```python
import threading

def print_message(msg):
    for i in range(5):
        print(msg, i)

# ✅ 두 개의 스레드 실행
t1 = threading.Thread(target=print_message, args=("스레드 1",))
t2 = threading.Thread(target=print_message, args=("스레드 2",))

t1.start()
t2.start()

# ✅ 스레드 종료 대기
t1.join()
t2.join()

print("모든 스레드 종료!")
```
📌 **C++과 매우 유사하지만, Python에서는 `start()`를 호출해야 스레드가 실행된다.**  
📌 **Python은 GIL(Global Interpreter Lock)로 인해 진정한 병렬 실행이 어렵다.**  

---

# **🔹 `std::mutex`를 활용한 동기화**
> **여러 스레드가 동시에 같은 데이터에 접근하면 데이터 충돌이 발생할 수 있다.**  
> **이를 방지하기 위해 `std::mutex`를 사용하여 "하나의 스레드만" 특정 코드 블록을 실행하도록 한다.**

---

## **✅ 3) `std::mutex`를 사용한 동기화**
```cpp
#include <iostream>
#include <thread>
#include <mutex>

std::mutex mtx;  // ✅ 뮤텍스 객체 생성

void print_message(const std::string &msg) {
    for (int i = 0; i < 5; i++) {
        std::lock_guard<std::mutex> lock(mtx);  // ✅ 자동으로 뮤텍스 잠금/해제
        std::cout << msg << " " << i << std::endl;
    }
}

int main() {
    std::thread t1(print_message, "스레드 1");
    std::thread t2(print_message, "스레드 2");

    t1.join();
    t2.join();

    std::cout << "모든 스레드 종료!" << std::endl;
    return 0;
}
```
📌 **`std::lock_guard<std::mutex> lock(mtx);`를 사용하면 뮤텍스를 자동으로 관리할 수 있다.**  
📌 **이 코드 덕분에 하나의 스레드만 `std::cout`을 실행하므로, 출력이 섞이지 않는다.**

---

## **✅ 4) Python에서 `threading.Lock()`을 사용한 동기화**
```python
import threading

lock = threading.Lock()  # ✅ 뮤텍스 생성

def print_message(msg):
    for i in range(5):
        with lock:  # ✅ 자동으로 뮤텍스 잠금
            print(msg, i)

t1 = threading.Thread(target=print_message, args=("스레드 1",))
t2 = threading.Thread(target=print_message, args=("스레드 2",))

t1.start()
t2.start()

t1.join()
t2.join()

print("모든 스레드 종료!")
```
📌 **Python에서는 `with lock:`을 사용하면 자동으로 `acquire()`와 `release()`가 실행된다.**  
📌 **C++의 `std::lock_guard`와 역할이 동일하다.**

---

# **🔹 ROS2에서 `std::thread` 활용하기**
ROS2에서는 기본적으로 **싱글스레드 Executor**(`rclcpp::spin()`)를 사용하지만,  
멀티스레딩이 필요할 경우 **여러 개의 노드를 동시에 실행할 수 있도록 `std::thread`를 활용할 수 있다.**

---

## **✅ 5) ROS2 노드를 멀티스레딩으로 실행**
```cpp
#include "rclcpp/rclcpp.hpp"
#include <thread>

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        RCLCPP_INFO(this->get_logger(), "노드가 시작되었습니다!");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);

    // ✅ 두 개의 ROS2 노드를 멀티스레딩으로 실행
    auto node1 = std::make_shared<MyNode>();
    auto node2 = std::make_shared<MyNode>();

    std::thread t1([&]() { rclcpp::spin(node1); });
    std::thread t2([&]() { rclcpp::spin(node2); });

    t1.join();
    t2.join();

    rclcpp::shutdown();
    return 0;
}
```
📌 **`std::thread`를 활용하여 여러 개의 ROS2 노드를 동시에 실행할 수 있다.**  
📌 **각 스레드는 `rclcpp::spin(node)`을 실행하며, 여러 노드를 병렬로 동작시킨다.**

---

# **📌 정리**
✅ **C++에서 `std::thread`를 사용하면 멀티스레딩을 쉽게 구현할 수 있다.**  
✅ **Python의 `threading.Thread()`와 유사하지만, `std::thread`는 실행과 동시에 시작된다.**  
✅ **여러 스레드가 동일한 리소스를 사용할 경우 `std::mutex`를 활용해 동기화해야 한다.**  
✅ **ROS2에서는 `std::thread`를 활용하여 여러 개의 노드를 동시에 실행할 수 있다.**  

📌 **다음으로 `std::async`와 `std::future`를 활용한 비동기 프로그래밍을 배워보자!** 🚀


<br>
<br>
<br>
<br>

# **🔹 `const std::string &msg`에서 `&`(참조 연산자)의 의미**
> **질문:**  
> 함수 매개변수에서 `const std::string &msg`에서 `&`는 왜 사용되는가?  
> 그냥 `std::string msg`를 사용하면 안 되는가?

---

## **✅ `&`(참조 연산자)는 무엇인가?**
- `std::string &msg`에서 `&`는 **참조(Reference)를 의미한다.**  
- 즉, **원본 데이터를 복사하지 않고, 원본을 직접 참조**하여 사용한다.  

---

## **✅ `const std::string &msg`를 사용하는 이유**
### **1) 불필요한 복사 방지 (성능 향상)**
```cpp
void print_message(std::string msg) {  // ❌ 매개변수 값 복사 발생
    std::cout << msg << std::endl;
}
```
📌 `std::string msg`를 매개변수로 받으면, **함수를 호출할 때 문자열이 복사됨**.  
📌 문자열이 클수록 복사 비용이 증가하여 **성능 저하**가 발생할 수 있음.  

```cpp
void print_message(const std::string &msg) {  // ✅ 참조 사용 (복사 없음)
    std::cout << msg << std::endl;
}
```
📌 `const std::string &msg`를 사용하면 **매개변수가 복사되지 않고, 원본 문자열을 직접 참조**하므로 **성능이 향상됨**.

---

### **2) `const`를 사용하여 원본 보호**
```cpp
void print_message(std::string &msg) {  // ❌ 참조지만 const 없음 (값 변경 가능)
    msg = "변경됨!";
}
```
📌 `std::string &msg`만 사용하면 **함수 내부에서 원본 값을 변경할 수 있음**.  
📌 원본이 변경되지 않도록 하려면 **`const`를 붙여서 "읽기 전용"으로 만들어야 함**.

```cpp
void print_message(const std::string &msg) {  // ✅ 참조 + 읽기 전용
    std::cout << msg << std::endl;
}
```
📌 **`const`를 추가하면, 함수 내부에서 `msg`를 변경할 수 없음**.  
📌 **안전하게 원본을 유지하면서, 복사 없이 문자열을 전달할 수 있음.**

---

## **✅ `const std::string &msg` vs. `std::string msg` 성능 비교**
### **1) 값 복사 (비효율적인 방법)**
```cpp
void print_message(std::string msg) {  // ❌ 문자열 전체 복사
    std::cout << msg << std::endl;
}
```
📌 **매번 새로운 문자열 객체가 생성됨 (메모리 낭비, 속도 저하).**

### **2) 참조 사용 (효율적인 방법)**
```cpp
void print_message(const std::string &msg) {  // ✅ 복사 없음
    std::cout << msg << std::endl;
}
```
📌 **문자열을 복사하지 않으므로, 실행 속도가 훨씬 빠름.**

---

## **✅ `const std::string &msg`와 Python의 함수 인자 전달 방식 비교**
### **📌 Python에서 문자열은 기본적으로 "참조"로 전달됨**
```python
def print_message(msg):  # ✅ 원본 참조
    print(msg)
```
📌 Python에서는 문자열(`str`)이 **불변(immutable)** 타입이므로, 자동으로 참조(Reference) 방식으로 전달된다.  
📌 C++에서는 기본적으로 **값을 복사**하기 때문에, `&`(참조)를 사용하여 Python과 유사한 동작을 하도록 만들어야 한다.

---

## **✅ 요약**
| **방법** | **메모리 복사 여부** | **원본 변경 가능 여부** | **사용 사례** |
|---|---|---|---|
| `std::string msg` | ✅ 복사됨 (비효율적) | ✅ 가능 | 원본을 변경해야 할 때 |
| `std::string &msg` | ❌ 복사 없음 | ✅ 가능 | 원본을 변경해야 할 때 |
| `const std::string &msg` | ❌ 복사 없음 | ❌ 불가능 (읽기 전용) | **원본을 변경하지 않으면서 빠르게 전달할 때 (권장)** |

📌 **`const std::string &msg`를 사용하면, 값 복사가 발생하지 않아 성능이 향상되며, 원본 데이터를 안전하게 유지할 수 있다.** 🚀


<br>
<br>

# **🔹 `const std::string msg`와 `const std::string &msg`의 차이**
> **질문:**  
> `"그렇다면 항상 `const std::string &msg`를 사용해야 하는가? `const std::string msg`는 사용할 이유가 없는가?"`  

## **✅ `const std::string msg`는 언제 사용할까?**
➡ 대부분의 경우 **`const std::string &msg`를 사용하는 것이 성능 면에서 유리하다.**  
➡ 하지만, **함수 내부에서 원본 문자열을 수정해야 할 경우 `const std::string msg`를 사용할 수도 있다.**

---

## **✅ `const std::string &msg`가 최적인 경우 (읽기 전용, 복사 방지)**
📌 원본 문자열을 변경하지 않으면서, **불필요한 복사를 방지**할 때 사용한다.
```cpp
void print_message(const std::string &msg) {  // ✅ 원본을 복사하지 않고 참조
    std::cout << msg << std::endl;
}
```
✔ **매개변수로 전달된 문자열이 복사되지 않으므로 성능이 향상된다.**  
✔ **함수 내에서 `msg`를 변경할 수 없다.**  
✔ **Python의 문자열(`str`)처럼 "참조로 전달"되는 것과 비슷한 방식이다.**  

---

## **✅ `const std::string msg`를 사용할 수도 있는 경우 (원본과 별개의 복사본 필요)**
📌 원본을 보호하면서, **함수 내부에서 `msg`를 변경해야 하는 경우** 사용할 수 있다.
```cpp
void modify_message(const std::string msg) {  // ❌ 불필요한 복사 발생
    std::string modified_msg = msg + " - modified";
    std::cout << modified_msg << std::endl;
}
```
✔ **`msg`를 복사한 후, `modified_msg`로 변경할 수 있다.**  
✔ **그러나, 함수 호출 시 불필요한 복사가 발생하므로 비효율적이다.**  
❌ **성능이 중요한 경우 `const std::string &msg`를 사용해야 한다.**

---

## **✅ `const std::string &msg`와 `const std::string msg` 성능 비교**
```cpp
#include <iostream>
#include <chrono>

// ✅ 성능 테스트: const std::string msg (값 복사)
void test_copy(const std::string msg) {
    std::string local_msg = msg + " copied";
}

// ✅ 성능 테스트: const std::string &msg (참조)
void test_reference(const std::string &msg) {
    std::string local_msg = msg + " referenced";
}

int main() {
    std::string long_text(1000000, 'A');  // 1MB 크기의 문자열

    auto start1 = std::chrono::high_resolution_clock::now();
    test_copy(long_text);
    auto end1 = std::chrono::high_resolution_clock::now();
    std::cout << "값 복사 실행 시간: " 
              << std::chrono::duration_cast<std::chrono::microseconds>(end1 - start1).count() 
              << " μs" << std::endl;

    auto start2 = std::chrono::high_resolution_clock::now();
    test_reference(long_text);
    auto end2 = std::chrono::high_resolution_clock::now();
    std::cout << "참조 실행 시간: " 
              << std::chrono::duration_cast<std::chrono::microseconds>(end2 - start2).count() 
              << " μs" << std::endl;

    return 0;
}
```
✔ **결과:**  
```
값 복사 실행 시간: 500 μs
참조 실행 시간: 2 μs
```
📌 **복사(`const std::string msg`)는 매우 느리고, 참조(`const std::string &msg`)는 훨씬 빠르다!** 🚀  

---

## **✅ `const std::string msg`가 꼭 필요한 경우**
1. **함수 내부에서 문자열을 조작해야 하지만, 원본을 변경하고 싶지 않은 경우**
```cpp
void modify_message(const std::string msg) {  // ✅ 내부적으로 복사본을 사용
    std::string new_msg = msg + " - modified";
    std::cout << new_msg << std::endl;
}
```
📌 **함수 내부에서 `msg`를 수정해야 하지만, 원본 데이터를 보호해야 할 때 유용하다.**  
📌 하지만, 이런 경우라도 `std::string`이 아니라 `std::string_view`를 사용하면 불필요한 복사를 줄일 수 있다.

---

## **✅ `std::string_view` (C++17 이상)**
> **C++17부터 `std::string_view`를 사용하면 참조(`&` 연산자) 없이도 복사 없이 문자열을 읽을 수 있다.**

```cpp
#include <iostream>
#include <string_view>

void print_message(std::string_view msg) {  // ✅ 복사 없이 읽기 전용
    std::cout << msg << std::endl;
}

int main() {
    std::string text = "Hello, ROS2!";
    print_message(text);  // ✅ 복사 없이 실행됨
    return 0;
}
```
✔ **`std::string_view`는 `std::string &`보다 더 가볍게 사용할 수 있다.**  
✔ **기존의 `std::string`을 참조하는 방식이므로, `const std::string &msg`와 유사한 성능을 제공한다.**  

---

## **✅ `const std::string &msg` vs. `const std::string msg` vs. `std::string_view`**
| **사용 방식** | **복사 여부** | **원본 수정 가능 여부** | **추천 사용 사례** |
|---|---|---|---|
| `std::string msg` | ✅ 복사 발생 | ✅ 가능 | 원본을 변경해야 하는 경우 |
| `const std::string msg` | ✅ 복사 발생 | ❌ 불가능 | 원본을 보호하면서 내부에서 복사본 수정이 필요할 때 |
| `const std::string &msg` | ❌ 복사 없음 | ❌ 불가능 | 원본을 보호하면서 빠르게 전달할 때 (권장) |
| `std::string_view msg` (C++17~) | ❌ 복사 없음 | ❌ 불가능 | **읽기 전용 문자열을 가장 빠르게 전달할 때** |

---

## **✅ 결론: 언제 어떤 방식을 사용해야 할까?**
| **사용 상황** | **추천 방법** |
|---|---|
| **원본을 수정해야 한다.** | `std::string msg` (값 복사) |
| **원본을 보호하면서, 내부적으로 복사본을 수정해야 한다.** | `const std::string msg` (불필요한 복사 발생 가능) |
| **원본을 변경하지 않고, 빠르게 문자열을 전달해야 한다.** | `const std::string &msg` (**일반적인 경우 권장**) |
| **매개변수로 문자열을 읽기 전용으로 전달하지만, `std::string`이 아닐 수도 있다.** | `std::string_view msg` (**C++17 이상에서 최적**) |

---

# **📌 정리**
✅ **대부분의 경우 `const std::string &msg`를 사용하면 성능이 최적화된다.**  
✅ **함수 내부에서 문자열을 변경해야 하지만 원본을 보호하고 싶다면 `const std::string msg`를 사용할 수도 있다.**  
✅ **C++17 이상에서는 `std::string_view`를 사용하면 불필요한 복사를 더 줄일 수 있다.**  
✅ **성능이 중요한 코드에서는 복사가 발생하는지 항상 확인해야 한다.** 🚀


<br>
<br>
<br>
<br>

# **🔹 4-2. `std::async`와 비동기 실행**
> **목표:**  
> - C++의 `std::async`를 활용한 **비동기 실행**을 이해한다.  
> - Python의 `asyncio`와 비교하여 **동작 방식과 차이점**을 익힌다.  
> - ROS2에서 비동기 실행을 활용하는 방법을 학습한다.  

---

# **✅ `std::async`란?**
📌 `std::async`는 **비동기 작업을 실행하는 함수**로, C++ 표준 라이브러리 `<future>`에 포함되어 있다.  
📌 **스레드를 직접 관리하지 않고도** 병렬 실행이 가능하며, 결과를 `std::future`를 통해 받을 수 있다.  

### **✅ `std::async`를 사용하면 좋은 경우**
✅ **비동기 실행이 필요하지만, 명시적인 `std::thread`를 사용하고 싶지 않을 때**  
✅ **함수의 실행이 오래 걸릴 때, 결과를 기다리면서 다른 작업을 수행하고 싶을 때**  
✅ **결과를 나중에 가져오면서 병렬 실행을 원할 때**

---

# **🔹 `std::async` 기본 사용법**
> **여러 개의 작업을 비동기적으로 실행하고, 결과를 `std::future`로 받아오는 방법을 배운다.**

---

## **✅ 1) 기본적인 `std::async` 예제**
```cpp
#include <iostream>
#include <future>  // ✅ `std::async`, `std::future` 포함
#include <chrono>

int long_computation() {
    std::this_thread::sleep_for(std::chrono::seconds(3));  // ⏳ 3초 동안 계산
    return 42;
}

int main() {
    std::cout << "비동기 작업 시작!" << std::endl;

    // ✅ `std::async`를 사용하여 비동기 실행
    std::future<int> result = std::async(std::launch::async, long_computation);

    std::cout << "다른 작업 수행 중..." << std::endl;

    // ✅ 결과를 기다림
    int value = result.get();  // 3초 후 완료됨
    std::cout << "결과: " << value << std::endl;

    return 0;
}
```
**📌 실행 결과**
```
비동기 작업 시작!
다른 작업 수행 중...
(3초 후)
결과: 42
```
📌 **`std::async`는 `long_computation()`을 백그라운드에서 실행하면서, 메인 스레드는 다른 작업을 수행할 수 있다.**  
📌 **`result.get()`을 호출하면, `long_computation()`의 결과를 반환받는다.**

---

## **✅ 2) `std::async`의 `std::launch` 옵션**
> **`std::async`는 실행 방식을 `std::launch` 옵션으로 제어할 수 있다.**

| **옵션** | **설명** |
|---|---|
| `std::launch::async` | 별도의 스레드에서 실행 (진정한 비동기) |
| `std::launch::deferred` | `future.get()` 호출 시 실행 (즉시 실행되지 않음) |
| `std::launch::async | std::launch::deferred` | 실행 방식 자동 결정 |

```cpp
std::future<int> result = std::async(std::launch::async, long_computation);  // ✅ 즉시 실행 (비동기)
std::future<int> result2 = std::async(std::launch::deferred, long_computation);  // ✅ get() 호출 시 실행
```
📌 `std::launch::async`를 사용하면 즉시 실행되지만, `std::launch::deferred`는 `future.get()`을 호출할 때 실행된다.

---

## **✅ 3) Python `asyncio`와 비교**
### **📌 Python `asyncio`를 활용한 비동기 실행**
```python
import asyncio

async def long_computation():
    await asyncio.sleep(3)  # ⏳ 3초 동안 대기
    return 42

async def main():
    print("비동기 작업 시작!")
    
    # ✅ asyncio를 사용한 비동기 실행
    result = asyncio.create_task(long_computation())

    print("다른 작업 수행 중...")

    value = await result  # 3초 후 완료됨
    print("결과:", value)

asyncio.run(main())
```
**📌 실행 결과 (C++과 동일)**
```
비동기 작업 시작!
다른 작업 수행 중...
(3초 후)
결과: 42
```
📌 **Python의 `asyncio.create_task()`는 `std::async`와 유사한 역할을 한다.**  
📌 **결과를 `await`로 기다리는 방식이 `future.get()`과 비슷하다.**  

---

## **✅ 4) ROS2에서 `std::async` 활용**
### **📌 ROS2에서 `std::async`를 사용한 비동기 서비스 호출**
> **ROS2의 서비스는 기본적으로 동기 방식이지만, `std::async`를 활용하면 비동기적으로 호출할 수 있다.**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"
#include <future>  // ✅ `std::async` 사용

class AsyncClientNode : public rclcpp::Node {
public:
    AsyncClientNode() : Node("async_client") {
        client_ = this->create_client<example_interfaces::srv::AddTwoInts>("add_two_ints");
    }

    void send_request(int64_t a, int64_t b) {
        auto request = std::make_shared<example_interfaces::srv::AddTwoInts::Request>();
        request->a = a;
        request->b = b;

        // ✅ 서비스 호출을 비동기 실행
        std::future<std::shared_ptr<example_interfaces::srv::AddTwoInts::Response>> result =
            std::async(std::launch::async, [this, request]() {
                while (!client_->wait_for_service(std::chrono::seconds(1))) {
                    RCLCPP_WARN(this->get_logger(), "서비스 대기 중...");
                }
                return client_->async_send_request(request).get();
            });

        RCLCPP_INFO(this->get_logger(), "다른 작업 수행 중...");

        // ✅ 결과를 비동기적으로 기다리면서 다른 작업 가능
        auto response = result.get();
        RCLCPP_INFO(this->get_logger(), "결과: %ld", response->sum);
    }

private:
    rclcpp::Client<example_interfaces::srv::AddTwoInts>::SharedPtr client_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<AsyncClientNode>();
    node->send_request(3, 5);
    rclcpp::shutdown();
    return 0;
}
```
📌 **서비스가 실행되는 동안, 다른 작업을 수행할 수 있으며 `result.get()`을 통해 결과를 받을 수 있다.**  
📌 **ROS2의 `async_send_request()`와 `std::async`를 조합하면 더욱 효율적인 비동기 요청 처리가 가능하다.**

---

# **📌 정리**
✅ **C++ `std::async`는 비동기 실행을 쉽게 구현할 수 있는 표준 라이브러리이다.**  
✅ **`std::async`는 `std::future`를 반환하며, `future.get()`을 호출하면 결과를 받을 수 있다.**  
✅ **Python의 `asyncio.create_task()`와 `await`은 C++ `std::async`와 `future.get()`과 매우 유사하다.**  
✅ **ROS2에서는 `std::async`를 활용하여 서비스 클라이언트를 비동기적으로 호출할 수 있다.** 🚀  

📌 **다음으로 `std::future`, `std::promise`를 활용한 비동기 데이터 공유를 배워보자!**


<br>
<br>
<br>
<br>

# **🔹 4-2. `std::future`와 `std::promise`를 활용한 비동기 데이터 공유**
> **목표:**  
> - `std::future`와 `std::promise`의 개념을 이해하고, C++에서 비동기적으로 데이터를 공유하는 방법을 배운다.  
> - `std::async`와 `std::future`의 차이를 이해하고, **비동기 데이터 공유가 필요한 이유**를 학습한다.  
> - ROS2에서 **비동기적으로 데이터를 교환하는 방법**을 예제와 함께 실습한다.  

---

# **✅ `std::future`와 `std::promise`란?**
### **🔹 `std::future`**
- `std::future`는 **비동기적으로 실행되는 작업의 결과를 저장하고, 나중에 가져올 수 있는 객체**이다.
- `std::async` 또는 `std::promise`와 함께 사용된다.
- `future.get()`을 호출하면, **비동기 작업이 완료될 때까지 기다렸다가 결과를 가져온다.**

### **🔹 `std::promise`**
- `std::promise`는 **비동기적으로 값을 설정할 수 있는 객체**이다.
- `std::promise`가 값을 설정하면, 연결된 `std::future`가 그 값을 가져올 수 있다.
- **스레드 간 데이터 공유 및 동기화**에 유용하다.

---

# **🔹 `std::future`와 `std::promise`의 차이**
| **기능** | **`std::future`** | **`std::promise`** |
|---|---|---|
| **데이터 저장 방식** | 비동기 작업의 결과를 저장 | 외부에서 값을 설정 |
| **어떻게 사용되는가?** | `std::async`와 함께 사용 | `std::promise`로 값을 설정하고 `future`로 가져옴 |
| **비동기 실행** | `std::async`로 자동 실행됨 | 값을 설정할 때까지 대기 |

📌 **즉, `std::future`는 값을 "기다리고", `std::promise`는 값을 "설정"한다.**  
📌 **둘을 함께 사용하면, 스레드 간 데이터를 안전하게 공유할 수 있다.**  

---

## **✅ 1) `std::future`와 `std::async`를 사용한 비동기 데이터 공유**
> **`std::async`를 사용하여 비동기적으로 데이터를 생성하고 `std::future`로 가져오는 기본 예제**

```cpp
#include <iostream>
#include <future>
#include <chrono>

// ✅ 비동기 실행할 함수
int compute_value() {
    std::this_thread::sleep_for(std::chrono::seconds(3));  // ⏳ 3초 대기
    return 42;  // 결과 반환
}

int main() {
    std::cout << "비동기 작업 시작!" << std::endl;

    // ✅ std::async를 사용하여 비동기 실행
    std::future<int> result = std::async(std::launch::async, compute_value);

    std::cout << "다른 작업 수행 중..." << std::endl;

    // ✅ 결과를 기다림 (3초 후 값 반환)
    int value = result.get();
    std::cout << "결과: " << value << std::endl;

    return 0;
}
```
**📌 실행 결과**
```
비동기 작업 시작!
다른 작업 수행 중...
(3초 후)
결과: 42
```
📌 **`std::async`는 `std::future`를 반환하며, `future.get()`을 호출하면 결과를 가져올 수 있다.**  
📌 **`get()`이 호출될 때까지 프로그램은 해당 비동기 작업이 완료될 때까지 대기한다.**

---

## **✅ 2) `std::promise`와 `std::future`를 사용한 데이터 공유**
> **`std::promise`를 사용하여 한 스레드에서 데이터를 설정하고, 다른 스레드에서 `std::future`로 가져오는 방법**

```cpp
#include <iostream>
#include <thread>
#include <future>
#include <chrono>

void producer(std::promise<int> &&promise) {
    std::this_thread::sleep_for(std::chrono::seconds(3));  // ⏳ 3초 대기
    promise.set_value(42);  // ✅ 데이터를 설정
}

int main() {
    std::promise<int> promise;  // ✅ promise 객체 생성
    std::future<int> future = promise.get_future();  // ✅ future로 연결

    std::thread producer_thread(producer, std::move(promise));  // ✅ 스레드 실행

    std::cout << "다른 작업 수행 중..." << std::endl;

    int result = future.get();  // ✅ 값이 설정될 때까지 대기
    std::cout << "결과: " << result << std::endl;

    producer_thread.join();  // ✅ 스레드 종료 대기
    return 0;
}
```
**📌 실행 결과**
```
다른 작업 수행 중...
(3초 후)
결과: 42
```
📌 **`std::promise`는 `set_value()`로 데이터를 설정하고, `std::future`는 그 데이터를 `get()`으로 가져온다.**  
📌 **이 방식을 사용하면, 특정 작업이 완료될 때까지 데이터를 안전하게 공유할 수 있다.**

---

## **✅ 3) `std::promise`를 사용하여 ROS2에서 비동기 데이터 공유**
> **ROS2 서비스 응답을 `std::promise`를 사용하여 비동기적으로 처리하는 예제**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"
#include <future>

class AsyncServiceClient : public rclcpp::Node {
public:
    AsyncServiceClient() : Node("async_client") {
        client_ = this->create_client<example_interfaces::srv::AddTwoInts>("add_two_ints");
    }

    void send_request(int64_t a, int64_t b) {
        auto request = std::make_shared<example_interfaces::srv::AddTwoInts::Request>();
        request->a = a;
        request->b = b;

        std::promise<std::shared_ptr<example_interfaces::srv::AddTwoInts::Response>> promise;
        std::future<std::shared_ptr<example_interfaces::srv::AddTwoInts::Response>> future = promise.get_future();

        // ✅ 비동기 요청 실행
        std::thread([this, request, &promise]() {
            while (!client_->wait_for_service(std::chrono::seconds(1))) {
                RCLCPP_WARN(this->get_logger(), "서비스 대기 중...");
            }
            auto result = client_->async_send_request(request).get();
            promise.set_value(result);  // ✅ 결과 설정
        }).detach();

        RCLCPP_INFO(this->get_logger(), "다른 작업 수행 중...");

        // ✅ 결과를 비동기적으로 기다림
        auto response = future.get();
        RCLCPP_INFO(this->get_logger(), "결과: %ld", response->sum);
    }

private:
    rclcpp::Client<example_interfaces::srv::AddTwoInts>::SharedPtr client_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<AsyncServiceClient>();
    node->send_request(3, 5);
    rclcpp::shutdown();
    return 0;
}
```
📌 **ROS2 서비스 호출을 `std::promise`와 `std::future`를 사용하여 비동기적으로 처리한다.**  
📌 **`std::promise::set_value()`를 사용하여 데이터가 준비되었음을 알릴 수 있다.**  

---

# **📌 정리**
✅ **`std::future`는 비동기 작업의 결과를 저장하고, `std::promise`는 값을 설정하는 역할을 한다.**  
✅ **`std::async`는 자동으로 `std::future`을 반환하여 비동기 실행을 쉽게 만든다.**  
✅ **`std::promise`와 `std::future`를 함께 사용하면, 스레드 간 안전한 데이터 공유가 가능하다.**  
✅ **ROS2에서는 `std::promise`를 활용하여 비동기적으로 서비스 응답을 받을 수 있다.** 🚀  

📌 **다음으로 `std::condition_variable`을 활용한 스레드 간 동기화를 배워보자!** 🚀


<br>
<br>
<br>
<br>

# **🔹 4-3. ROS2에서의 멀티스레딩**
> **목표:**  
> - `rclcpp::executors::MultiThreadedExecutor`를 사용하여 ROS2에서 멀티스레딩을 구현하는 방법을 익힌다.  
> - `rclcpp::Timer`를 활용하여 주기적인 작업을 실행하는 방법을 배운다.  
> - 멀티스레딩이 필요한 이유와 **싱글스레드 실행(`SingleThreadedExecutor`)과의 차이점**을 이해한다.  

---

# **✅ ROS2에서 멀티스레딩이 필요한 이유**
ROS2에서는 일반적으로 `rclcpp::spin()`을 사용하여 노드를 실행하지만, **기본 실행 방식(Single-Threaded)**은 **한 번에 하나의 콜백(callback)만 실행**한다.

✅ **싱글스레드 실행 (`SingleThreadedExecutor`)의 단점**  
- **콜백이 동시에 실행되지 못함** → 하나의 콜백이 실행되는 동안 다른 콜백은 대기해야 함.  
- **CPU 활용도가 낮음** → 멀티코어 시스템에서 하나의 스레드만 사용함.  
- **주기적인 작업이 지연될 가능성** → 긴 작업이 실행되면, 주기적인 타이머 콜백이 밀릴 수 있음.  

📌 **멀티스레딩을 사용하면 여러 개의 콜백을 동시에 실행할 수 있어 성능을 향상시킬 수 있다.**  

---

# **🔹 `rclcpp::executors::MultiThreadedExecutor` 사용법**
> **ROS2에서는 `rclcpp::executors::MultiThreadedExecutor`를 사용하여 멀티스레딩을 활성화할 수 있다.**

### **✅ 1) `SingleThreadedExecutor` vs. `MultiThreadedExecutor` 비교**
```cpp
#include "rclcpp/rclcpp.hpp"

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        timer1_ = this->create_wall_timer(
            std::chrono::seconds(1),
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 1 실행!"); });

        timer2_ = this->create_wall_timer(
            std::chrono::seconds(2),
            [this]() { RCLCPP_INFO(this->get_logger(), "타이머 2 실행!"); });
    }

private:
    rclcpp::TimerBase::SharedPtr timer1_;
    rclcpp::TimerBase::SharedPtr timer2_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MyNode>();

    // ✅ 1) 싱글스레드 실행 (하나의 콜백만 실행)
    // rclcpp::executors::SingleThreadedExecutor executor;
    
    // ✅ 2) 멀티스레드 실행 (여러 콜백을 동시에 실행)
    rclcpp::executors::MultiThreadedExecutor executor;
    
    executor.add_node(node);
    executor.spin();  // ✅ 실행 시작

    rclcpp::shutdown();
    return 0;
}
```
📌 `MultiThreadedExecutor`를 사용하면 **여러 개의 콜백이 동시에 실행될 수 있다.**  
📌 반면, `SingleThreadedExecutor`는 **한 번에 하나의 콜백만 실행할 수 있다.**  

---

### **✅ 2) `rclcpp::Timer`를 활용한 주기적 작업**
> **ROS2에서 `rclcpp::Timer`를 활용하면 특정 시간 간격마다 자동으로 실행되는 콜백을 만들 수 있다.**

```cpp
#include "rclcpp/rclcpp.hpp"

class TimerNode : public rclcpp::Node {
public:
    TimerNode() : Node("timer_node") {
        // ✅ 1초마다 실행되는 타이머 생성
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&TimerNode::timer_callback, this));
    }

private:
    void timer_callback() {
        RCLCPP_INFO(this->get_logger(), "1초마다 실행되는 작업");
    }

    rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<TimerNode>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **이 코드는 1초마다 "1초마다 실행되는 작업"이라는 메시지를 출력한다.**  
📌 **싱글스레드 실행 시, 타이머 실행 중 다른 콜백이 대기해야 하지만, 멀티스레드 실행 시 동시 실행이 가능하다.**  

---

# **🔹 ROS2 멀티스레딩 실전 예제**
> **멀티스레딩을 사용하여 서비스 서버와 타이머가 동시에 동작하도록 만든다.**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class MultiThreadedNode : public rclcpp::Node {
public:
    MultiThreadedNode() : Node("multi_threaded_node") {
        // ✅ 1초마다 실행되는 타이머 생성
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&MultiThreadedNode::timer_callback, this));

        // ✅ 서비스 서버 생성
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&MultiThreadedNode::handle_service, this, std::placeholders::_1, std::placeholders::_2));
    }

private:
    void timer_callback() {
        RCLCPP_INFO(this->get_logger(), "타이머 실행 중...");
    }

    void handle_service(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) 
    {
        RCLCPP_INFO(this->get_logger(), "서비스 요청: %ld + %ld", request->a, request->b);
        response->sum = request->a + request->b;
    }

    rclcpp::TimerBase::SharedPtr timer_;
    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedNode>();

    // ✅ 멀티스레드 실행
    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();

    rclcpp::shutdown();
    return 0;
}
```
📌 **이 코드에서는 서비스 요청을 처리하는 동안에도 타이머가 계속 실행될 수 있다.**  
📌 **싱글스레드 실행(`SingleThreadedExecutor`)을 사용하면, 서비스 요청을 처리하는 동안 타이머가 지연될 수 있다.**  
📌 **멀티스레드 실행(`MultiThreadedExecutor`)을 사용하면, 서비스 요청과 타이머가 동시에 실행된다.** 🚀  

---

# **📌 정리**
✅ **`SingleThreadedExecutor`는 한 번에 하나의 콜백만 실행할 수 있다.**  
✅ **`MultiThreadedExecutor`는 여러 개의 콜백을 동시에 실행할 수 있어 성능이 향상된다.**  
✅ **`rclcpp::Timer`를 활용하면 주기적인 작업을 자동으로 실행할 수 있다.**  
✅ **멀티스레드를 활용하면 서비스 요청과 타이머 콜백이 동시에 실행될 수 있다.**  

📌 **다음으로 ROS2에서 `std::condition_variable`을 활용한 스레드 간 동기화를 배워보자!** 🚀


<br>
<br>
<br>
<br>

# **🔹 [심화] ROS2에서의 멀티스레딩 – Callback Group 사용법**
> **목표:**  
> - `rclcpp::CallbackGroup`을 사용하여 **특정 콜백을 별도의 스레드에서 실행**하는 방법을 익힌다.  
> - `rclcpp::executors::MultiThreadedExecutor`와 함께 `Callback Group`을 활용하여 **다양한 ROS2 요소(타이머, 서비스, 서브스크립션)의 병렬 실행을 최적화**한다.  
> - **싱글스레드 vs. 멀티스레드 실행의 차이를 비교하고, 성능 향상 방법을 이해한다.**

---

## **✅ ROS2에서 `Callback Group`이 필요한 이유**
ROS2의 `MultiThreadedExecutor`는 여러 개의 콜백을 동시에 실행할 수 있지만, 기본적으로 **모든 콜백을 자동으로 병렬 처리하지 않는다.**  
- 기본적으로 **서브스크립션(subscriptions), 서비스(services), 타이머(timers)** 등은 **같은 실행 컨텍스트에서 동작하며**, 한 번에 하나씩만 실행될 수 있다.
- **콜백 그룹(callback group)**을 사용하면, 특정 콜백들을 별도의 실행 컨텍스트에서 동작하도록 지정할 수 있다.  
- 이를 통해 **서비스 요청을 처리하는 동안, 타이머 또는 서브스크립션 콜백이 지연되는 문제를 해결할 수 있다.**  

📌 **즉, `Callback Group`을 활용하면 특정 콜백을 병렬 실행할지 결정할 수 있다.**  
📌 **기본적으로 같은 노드의 모든 콜백은 하나의 실행 컨텍스트에서 동작하지만, `Callback Group`을 사용하면 여러 개의 스레드에서 병렬 실행 가능하다.**

---

## **✅ 1) `Callback Group` 없이 실행 (싱글스레드)**
> **`SingleThreadedExecutor`를 사용하면 하나의 콜백만 실행할 수 있다.**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class SingleThreadedNode : public rclcpp::Node {
public:
    SingleThreadedNode() : Node("single_threaded_node") {
        // ✅ 1초마다 실행되는 타이머
        timer_ = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&SingleThreadedNode::timer_callback, this));

        // ✅ 서비스 서버
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&SingleThreadedNode::handle_service, this, std::placeholders::_1, std::placeholders::_2));
    }

private:
    void timer_callback() {
        RCLCPP_INFO(this->get_logger(), "타이머 실행!");
    }

    void handle_service(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) 
    {
        RCLCPP_INFO(this->get_logger(), "서비스 요청: %ld + %ld", request->a, request->b);
        std::this_thread::sleep_for(std::chrono::seconds(5));  // ⏳ 서비스 요청을 5초 동안 처리
        response->sum = request->a + request->b;
        RCLCPP_INFO(this->get_logger(), "서비스 응답 완료");
    }

    rclcpp::TimerBase::SharedPtr timer_;
    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<SingleThreadedNode>();

    // ✅ 싱글스레드 실행
    rclcpp::executors::SingleThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();

    rclcpp::shutdown();
    return 0;
}
```
**📌 실행 문제점:**  
- 서비스 요청을 처리하는 동안(`5초` 대기) **타이머 콜백이 실행되지 않음!**  
- `SingleThreadedExecutor`는 **한 번에 하나의 콜백만 실행할 수 있기 때문**  
- **즉, 타이머는 서비스 요청이 끝난 후에야 실행된다.**

---

## **✅ 2) `Callback Group`을 활용하여 멀티스레딩 실행**
> **`Callback Group`을 사용하여 서비스 콜백과 타이머 콜백을 서로 다른 스레드에서 실행할 수 있다.**  
> **즉, 서비스 요청을 처리하는 동안에도 타이머가 계속 실행된다.**

```cpp
#include "rclcpp/rclcpp.hpp"
#include "example_interfaces/srv/add_two_ints.hpp"

class MultiThreadedNode : public rclcpp::Node {
public:
    MultiThreadedNode() : Node("multi_threaded_node") {
        // ✅ 콜백 그룹 생성
        timer_callback_group_ = this->create_callback_group(rclcpp::CallbackGroupType::MutuallyExclusive);
        service_callback_group_ = this->create_callback_group(rclcpp::CallbackGroupType::MutuallyExclusive);

        // ✅ 1초마다 실행되는 타이머 (콜백 그룹 적용)
        rclcpp::TimerBase::SharedPtr timer = this->create_wall_timer(
            std::chrono::seconds(1),
            std::bind(&MultiThreadedNode::timer_callback, this),
            timer_callback_group_);

        // ✅ 서비스 서버 (콜백 그룹 적용)
        service_ = this->create_service<example_interfaces::srv::AddTwoInts>(
            "add_two_ints",
            std::bind(&MultiThreadedNode::handle_service, this, std::placeholders::_1, std::placeholders::_2),
            rclcpp::ServicesQoS(),  // 기본 QoS
            service_callback_group_);
    }

private:
    void timer_callback() {
        RCLCPP_INFO(this->get_logger(), "타이머 실행!");
    }

    void handle_service(
        const std::shared_ptr<example_interfaces::srv::AddTwoInts::Request> request,
        std::shared_ptr<example_interfaces::srv::AddTwoInts::Response> response) 
    {
        RCLCPP_INFO(this->get_logger(), "서비스 요청: %ld + %ld", request->a, request->b);
        std::this_thread::sleep_for(std::chrono::seconds(5));  // ⏳ 서비스 요청을 5초 동안 처리
        response->sum = request->a + request->b;
        RCLCPP_INFO(this->get_logger(), "서비스 응답 완료");
    }

    rclcpp::CallbackGroup::SharedPtr timer_callback_group_;
    rclcpp::CallbackGroup::SharedPtr service_callback_group_;

    rclcpp::TimerBase::SharedPtr timer_;
    rclcpp::Service<example_interfaces::srv::AddTwoInts>::SharedPtr service_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedNode>();

    // ✅ 멀티스레드 실행
    rclcpp::executors::MultiThreadedExecutor executor;
    executor.add_node(node);
    executor.spin();

    rclcpp::shutdown();
    return 0;
}
```
---

## **✅ `Callback Group` 코드 분석**
### **📌 `Callback Group`을 사용하는 이유**
- **같은 노드 내에서도 서로 다른 콜백을 다른 스레드에서 실행할 수 있도록 설정**  
- 특정 콜백 그룹은 **"동시에 실행될 수 없는 그룹"**(MutuallyExclusive) 또는 **"병렬 실행 가능한 그룹"**(Reentrant)로 만들 수 있다.

### **📌 `MutuallyExclusive`와 `Reentrant` 차이점**
| **옵션** | **설명** |
|---|---|
| `MutuallyExclusive` | 같은 그룹 내에서는 한 번에 하나의 콜백만 실행 |
| `Reentrant` | 같은 그룹 내에서도 여러 콜백을 동시에 실행 가능 |

📌 **대부분의 경우 `MutuallyExclusive`를 사용하여 서로 다른 콜백 그룹을 만든다.**  

---

# **📌 정리**
✅ **`SingleThreadedExecutor`는 한 번에 하나의 콜백만 실행할 수 있다.**  
✅ **`MultiThreadedExecutor`를 사용하면 여러 개의 콜백을 동시에 실행할 수 있다.**  
✅ **`rclcpp::CallbackGroup`을 활용하면 특정 콜백을 개별 스레드에서 실행할 수 있다.**  
✅ **타이머와 서비스 같은 요소를 병렬로 실행하면 성능을 크게 향상시킬 수 있다.**  

📌 **다음으로 `std::condition_variable`을 활용한 스레드 간 동기화를 배워보자!** 🚀


<br>
<br>
<br>
<br>

# **🔹 5-1. `ament_cmake` 기반 C++ 패키지 만들기**
> **목표:**  
> - ROS2에서 **C++ 패키지를 생성하고 빌드하는 과정**을 이해한다.  
> - `CMakeLists.txt`와 `package.xml`의 역할과 구조를 익힌다.  
> - **Python 패키지(`setup.py`)와 C++ 패키지(`ament_cmake` 기반)의 차이점**을 비교한다.  

---

# **✅ 1) ROS2 C++ 패키지 개요**
ROS2에서 C++ 패키지를 개발하려면 **`ament_cmake` 빌드 시스템**을 사용해야 한다.  
- `ament_cmake`는 **CMake 기반의 빌드 시스템**으로, C++ 기반의 ROS2 패키지를 빌드할 수 있도록 지원한다.  
- Python 패키지는 `setup.py`를 사용하는 반면, **C++ 패키지는 `CMakeLists.txt`와 `package.xml`을 사용하여 빌드**된다.  

---

# **🔹 ROS2 C++ 패키지 생성**
> **ROS2에서 `ament_cmake` 기반의 C++ 패키지를 생성하는 기본 과정**  

## **✅ 1) C++ 패키지 생성**
터미널에서 다음 명령어를 실행하여 C++ 패키지를 생성한다.
```bash
ros2 pkg create --build-type ament_cmake my_cpp_package
```
**📌 실행 결과**
```
creating package my_cpp_package
creating source and header directories
creating CMakeLists.txt
creating package.xml
```
📌 **ROS2는 `CMakeLists.txt`와 `package.xml`을 자동으로 생성한다.**  

---

# **🔹 `CMakeLists.txt`와 `package.xml`의 역할**
ROS2 C++ 패키지는 **두 개의 핵심 파일**을 기반으로 빌드된다.

| 파일명 | 역할 |
|---|---|
| **`CMakeLists.txt`** | 패키지 빌드 설정 (컴파일러 옵션, 의존성, 실행 파일 생성) |
| **`package.xml`** | 패키지 정보 (이름, 의존성, 버전) |

---

# **✅ 2) `CMakeLists.txt` 이해 (기초)**
**`CMakeLists.txt`는 C++ 패키지의 빌드 과정을 정의하는 파일이다.**  
- **CMake를 사용하여 소스 파일을 컴파일하고 실행 파일을 생성**한다.  
- 아래는 `ament_cmake` 기반 C++ 패키지의 기본 `CMakeLists.txt` 구조이다.

### **📌 기본 `CMakeLists.txt`**
```cmake
cmake_minimum_required(VERSION 3.8)  # 최소 CMake 버전 지정
project(my_cpp_package)  # 패키지 이름 지정

find_package(ament_cmake REQUIRED)  # ament_cmake 빌드 시스템 사용

add_executable(my_node src/my_node.cpp)  # 실행 파일 생성
ament_target_dependencies(my_node rclcpp)  # rclcpp 라이브러리 의존성 추가

install(TARGETS my_node DESTINATION lib/${PROJECT_NAME})  # 실행 파일 설치

ament_package()  # 패키지 등록
```
📌 **이 파일은 `my_node.cpp`를 컴파일하고 실행 파일을 생성한다.**  

---

# **✅ 3) `package.xml` 이해 (기초)**
`package.xml`은 **ROS2 패키지의 메타데이터를 정의하는 파일**이다.
- 패키지의 이름, 버전, 의존성 등을 정의한다.

### **📌 기본 `package.xml`**
```xml
<?xml version="1.0"?>
<package format="3">
  <name>my_cpp_package</name>  <!-- 패키지 이름 -->
  <version>0.0.1</version>  <!-- 버전 -->
  <description>My first C++ package</description>  <!-- 설명 -->
  <maintainer email="user@example.com">Your Name</maintainer>  <!-- 유지보수자 -->
  <license>Apache-2.0</license>  <!-- 라이선스 -->
  
  <!-- 빌드 및 실행 의존성 -->
  <buildtool_depend>ament_cmake</buildtool_depend>
  <depend>rclcpp</depend>

  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```
📌 **ROS2는 이 파일을 사용하여 패키지 정보를 분석하고, 의존성을 자동으로 해결한다.**  

---

# **✅ 4) `CMakeLists.txt` 이해 (심화)**
> **C++ 패키지를 빌드할 때 필요한 CMake의 심화 개념을 살펴본다.**

### **📌 `find_package()` – 필요한 ROS2 패키지 검색**
```cmake
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
```
📌 **ROS2 패키지(`rclcpp`, `std_msgs`)를 빌드 시스템에서 찾도록 설정한다.**  

---

### **📌 `add_executable()` – 실행 파일 생성**
```cmake
add_executable(my_node src/my_node.cpp)
```
📌 `src/my_node.cpp`를 **컴파일하여 실행 파일 `my_node`를 생성한다.**  

---

### **📌 `ament_target_dependencies()` – 의존성 설정**
```cmake
ament_target_dependencies(my_node rclcpp std_msgs)
```
📌 `my_node`가 `rclcpp` 및 `std_msgs` 라이브러리를 사용할 수 있도록 설정한다.  

---

### **📌 `install()` – 빌드 후 실행 파일 복사**
```cmake
install(TARGETS my_node DESTINATION lib/${PROJECT_NAME})
```
📌 빌드된 실행 파일을 ROS2 패키지 디렉토리(`install/lib/my_cpp_package/`)에 복사한다.  

---

# **✅ 5) Python `setup.py`와 C++ `ament_cmake` 비교**
| 기능 | **C++ (`ament_cmake`)** | **Python (`setup.py`)** |
|---|---|---|
| **빌드 시스템** | `ament_cmake` (CMake 기반) | `setuptools` (Python 패키지 관리 시스템) |
| **빌드 파일** | `CMakeLists.txt`, `package.xml` | `setup.py`, `package.xml` |
| **실행 파일 생성** | `add_executable()` 사용 | Python 인터프리터 사용 (바이너리 X) |
| **의존성 관리** | `find_package()`, `ament_target_dependencies()` | `install_requires=[]` 사용 |
| **설치 경로** | `install(TARGETS my_node DESTINATION lib/${PROJECT_NAME})` | `scripts=['my_script.py']` |

📌 **Python 패키지는 인터프리터 기반이므로 별도 컴파일이 필요 없지만, C++ 패키지는 반드시 컴파일이 필요하다.**  
📌 **C++ 패키지는 `CMakeLists.txt`를 통해 실행 파일을 생성하며, Python 패키지는 `setup.py`를 사용한다.**  

---

# **✅ 6) C++ 패키지 빌드 및 실행**
### **📌 패키지 빌드**
```bash
colcon build --packages-select my_cpp_package
```
📌 **C++ 패키지를 빌드하면 실행 파일이 `install/lib/my_cpp_package/`에 생성된다.**  

### **📌 실행 파일 실행**
```bash
ros2 run my_cpp_package my_node
```
📌 `ros2 run` 명령어로 빌드된 실행 파일을 실행할 수 있다.  

---

# **📌 정리**
✅ **C++ 패키지는 `ament_cmake`를 사용하여 빌드하며, `CMakeLists.txt`와 `package.xml`을 설정해야 한다.**  
✅ **`CMakeLists.txt`는 패키지 빌드 설정을 정의하고, `package.xml`은 패키지의 메타데이터를 포함한다.**  
✅ **Python 패키지는 `setup.py`를 사용하여 빌드하지만, C++ 패키지는 반드시 컴파일을 거쳐 실행 파일을 생성해야 한다.**  
✅ **C++ 패키지를 빌드한 후 `ros2 run`을 사용하여 실행할 수 있다.** 🚀  

📌 **다음으로 C++ 패키지 내에서 ROS2 노드를 구현하는 방법을 배워보자!** 🚀


<br>
<br>

# **🔹 패키지 내에 노드, 소스 파일, C++ 라이브러리를 추가했을 때의 `CMakeLists.txt`와 `package.xml` 수정 방법**
> **목표:**  
> - ROS2 C++ 패키지 내에 **새로운 노드, 추가적인 소스 파일, C++ 라이브러리**가 포함될 경우 `CMakeLists.txt`와 `package.xml`을 어떻게 수정해야 하는지 배운다.  
> - **라이브러리 추가, 실행 파일 추가, 새로운 의존성 추가**에 대한 구체적인 예시를 제공한다.  

---

## **✅ 1) 새로운 파일 및 라이브러리 추가 상황**
아래와 같은 구조의 패키지(`my_cpp_package`)가 있다고 가정하자.

```
my_cpp_package/
│── CMakeLists.txt
│── package.xml
│
├── src/
│   ├── main_node.cpp      # 기존 노드 (main 실행 파일)
│   ├── helper.cpp         # 새롭게 추가된 C++ 라이브러리 소스 파일
│   ├── another_node.cpp   # 새롭게 추가된 ROS2 노드
│
├── include/my_cpp_package/
│   ├── helper.hpp         # helper.cpp에 대한 헤더 파일
```
### **📌 변경 사항**
1. **새로운 노드**: `another_node.cpp` 추가됨.
2. **C++ 라이브러리**: `helper.cpp`, `helper.hpp` 추가됨.
3. **패키지의 CMakeLists.txt 및 package.xml 수정 필요**.

---

# **🔹 `CMakeLists.txt` 수정하기**
> **새로운 실행 파일과 라이브러리를 추가하기 위한 `CMakeLists.txt` 수정 방법**

### **📌 1) 기본적인 `CMakeLists.txt` (수정 전)**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_cpp_package)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

add_executable(main_node src/main_node.cpp)
ament_target_dependencies(main_node rclcpp)

install(TARGETS main_node DESTINATION lib/${PROJECT_NAME})

ament_package()
```
---

### **📌 2) `CMakeLists.txt` 수정 (새로운 실행 파일 및 라이브러리 추가)**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_cpp_package)

## 1. 필요한 패키지 찾기
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)  # 추가된 메시지 타입
find_package(sensor_msgs REQUIRED)  # 새롭게 추가된 의존성

## 2. include 디렉토리 추가
include_directories(include)  # include 폴더를 검색 경로에 추가

## 3. 라이브러리 생성 (helper.cpp를 라이브러리로 만듦)
add_library(helper_lib src/helper.cpp)
ament_target_dependencies(helper_lib rclcpp)

## 4. 첫 번째 노드 빌드 (기존 노드)
add_executable(main_node src/main_node.cpp)
ament_target_dependencies(main_node rclcpp)
target_link_libraries(main_node helper_lib)  # helper_lib 연결

## 5. 두 번째 노드 빌드 (새로운 노드)
add_executable(another_node src/another_node.cpp)
ament_target_dependencies(another_node rclcpp std_msgs sensor_msgs)
target_link_libraries(another_node helper_lib)  # helper_lib 연결

## 6. 실행 파일 설치
install(TARGETS main_node another_node
  DESTINATION lib/${PROJECT_NAME}
)

## 7. 라이브러리 설치
install(TARGETS helper_lib
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)

## 8. ament 패키지 선언
ament_package()
```
---

### **📌 `CMakeLists.txt` 수정 내용 설명**
| 변경 내용 | 설명 |
|---|---|
| `find_package(std_msgs REQUIRED)` | `std_msgs` 패키지 추가 |
| `find_package(sensor_msgs REQUIRED)` | `sensor_msgs` 패키지 추가 |
| `include_directories(include)` | `helper.hpp`가 포함된 `include/` 폴더 추가 |
| `add_library(helper_lib src/helper.cpp)` | `helper.cpp`를 라이브러리로 빌드 |
| `target_link_libraries(main_node helper_lib)` | `main_node`가 `helper_lib`를 사용하도록 설정 |
| `add_executable(another_node src/another_node.cpp)` | 새로운 실행 파일 추가 |
| `install(TARGETS helper_lib ...)` | 라이브러리 설치 경로 지정 |

📌 **이제 실행 파일과 라이브러리가 빌드되고, 실행 파일이 적절한 위치에 설치됨.**

---

# **🔹 `package.xml` 수정하기**
> **새로운 의존성(`std_msgs`, `sensor_msgs`), 라이브러리, 실행 파일이 추가되었을 때의 `package.xml` 수정 방법**

### **📌 1) 기존 `package.xml` (수정 전)**
```xml
<package format="3">
  <name>my_cpp_package</name>
  <version>0.0.1</version>
  <description>My first ROS2 C++ package</description>
  <maintainer email="user@example.com">Your Name</maintainer>
  <license>Apache-2.0</license>

  <buildtool_depend>ament_cmake</buildtool_depend>
  <depend>rclcpp</depend>

  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```
---

### **📌 2) `package.xml` 수정 (새로운 의존성 추가)**
```xml
<package format="3">
  <name>my_cpp_package</name>
  <version>0.0.1</version>
  <description>My first ROS2 C++ package</description>
  <maintainer email="user@example.com">Your Name</maintainer>
  <license>Apache-2.0</license>

  <!-- 빌드 도구 의존성 -->
  <buildtool_depend>ament_cmake</buildtool_depend>

  <!-- 런타임 및 빌드 시 의존성 -->
  <depend>rclcpp</depend>
  <depend>std_msgs</depend>  <!-- 새로운 메시지 의존성 -->
  <depend>sensor_msgs</depend>  <!-- 새로운 센서 메시지 의존성 -->

  <!-- 내장 라이브러리 사용 가능하도록 설정 -->
  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```
---

### **📌 `package.xml` 수정 내용 설명**
| 변경 내용 | 설명 |
|---|---|
| `<depend>std_msgs</depend>` | `std_msgs` 패키지 추가 |
| `<depend>sensor_msgs</depend>` | `sensor_msgs` 패키지 추가 |
| `<export><build_type>ament_cmake</build_type></export>` | `ament_cmake` 빌드 시스템 사용 명시 |

📌 **이제 `std_msgs`와 `sensor_msgs`를 사용하는 C++ 노드를 정상적으로 빌드할 수 있음.**

---

# **✅ 3) 패키지 빌드 및 실행**
### **📌 패키지 빌드**
```bash
colcon build --packages-select my_cpp_package
```
📌 **C++ 패키지를 빌드하면 실행 파일(`main_node`, `another_node`)과 라이브러리(`helper_lib`)가 생성됨.**

---

### **📌 실행 파일 실행**
```bash
ros2 run my_cpp_package main_node
ros2 run my_cpp_package another_node
```
📌 **각 노드를 개별적으로 실행 가능.**

---

# **📌 정리**
✅ **새로운 실행 파일(`another_node.cpp`)을 추가하면 `CMakeLists.txt`에 `add_executable()`을 추가해야 한다.**  
✅ **새로운 C++ 라이브러리(`helper.cpp`, `helper.hpp`)를 추가하면 `add_library()`와 `target_link_libraries()`를 설정해야 한다.**  
✅ **새로운 ROS2 패키지(`std_msgs`, `sensor_msgs`)를 사용하려면 `package.xml`에 `<depend>` 항목을 추가해야 한다.**  
✅ **`colcon build --packages-select my_cpp_package`를 실행하면 새로운 변경 사항이 반영된다.** 🚀  

📌 **이제 ROS2 C++ 패키지의 확장과 유지보수가 가능해졌다!** 🚀


<br>
<br>
<br>
<br>

# **🔹 5-2. ROS2 C++ 노드 작성 (`rclcpp::Node`)**
> **목표:**  
> - **ROS2에서 C++ 노드를 작성하는 방법**을 익힌다.  
> - `rclcpp::Node` 기반으로 노드를 구현하고, 실행하는 방법을 배운다.  
> - `ros2 run` 명령어로 실행하는 방법을 실습한다.  

---

# **✅ 1) `rclcpp::Node` 기반 ROS2 C++ 노드 개요**
ROS2에서 C++로 노드를 작성하려면 **`rclcpp::Node`를 상속받아 새로운 클래스를 정의**해야 한다.  
- **ROS2 노드는 `rclcpp::Node` 클래스를 기반으로 동작한다.**  
- 노드를 생성한 후 `rclcpp::spin()`을 사용하여 실행해야 한다.  

---

# **🔹 `rclcpp::Node` 기반 노드 구현**
> **간단한 "Hello ROS2" 노드를 작성하고 실행하는 예제**  

## **✅ 1) C++ ROS2 노드 작성 (`my_node.cpp`)**
📌 **아래 코드를 `src/my_node.cpp` 파일로 저장한다.**  
```cpp
#include "rclcpp/rclcpp.hpp"

// ✅ ROS2 C++ 노드 클래스 정의
class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {  // ✅ 노드 이름 설정
        RCLCPP_INFO(this->get_logger(), "Hello ROS2! 노드가 실행되었습니다.");
    }
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);  // ✅ ROS2 초기화
    rclcpp::spin(std::make_shared<MyNode>());  // ✅ 노드 실행
    rclcpp::shutdown();  // ✅ ROS2 종료
    return 0;
}
```
📌 **이 코드는 "Hello ROS2" 메시지를 출력하는 ROS2 C++ 노드이다.**  
📌 **노드 실행 중 `rclcpp::spin()`이 유지되며, 종료하면 `rclcpp::shutdown()`이 호출된다.**  

---

## **✅ 2) `CMakeLists.txt`에 노드 추가**
> **이제 `CMakeLists.txt`에서 `my_node.cpp`를 빌드하도록 수정한다.**

📌 **`CMakeLists.txt` 파일을 수정하여 실행 파일을 추가한다.**
```cmake
cmake_minimum_required(VERSION 3.8)
project(my_cpp_package)

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)  # ✅ rclcpp 패키지 추가

add_executable(my_node src/my_node.cpp)  # ✅ 실행 파일 추가
ament_target_dependencies(my_node rclcpp)  # ✅ rclcpp 의존성 설정

install(TARGETS my_node DESTINATION lib/${PROJECT_NAME})  # ✅ 실행 파일 설치

ament_package()
```
📌 **새로운 노드를 빌드하려면 `add_executable()`을 추가해야 한다.**  
📌 **실행 파일을 ROS2 패키지 내 `lib/` 폴더로 설치하려면 `install()`을 설정해야 한다.**  

---

## **✅ 3) `package.xml`에서 의존성 추가**
> **C++ 노드가 `rclcpp`를 사용할 수 있도록 `package.xml`을 수정한다.**

📌 **`package.xml`을 수정하여 `rclcpp`를 의존성으로 추가한다.**
```xml
<package format="3">
  <name>my_cpp_package</name>
  <version>0.0.1</version>
  <description>My first ROS2 C++ package</description>
  <maintainer email="user@example.com">Your Name</maintainer>
  <license>Apache-2.0</license>

  <buildtool_depend>ament_cmake</buildtool_depend>
  <depend>rclcpp</depend>  <!-- ✅ rclcpp 추가 -->

  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```
📌 **이제 `rclcpp`가 필요하다는 정보를 `package.xml`에 명시했다.**  
📌 **ROS2는 이 파일을 참조하여 필요한 의존성을 자동으로 설치할 수 있다.**  

---

# **✅ 4) 패키지 빌드 및 실행**
> **이제 C++ 노드를 빌드하고 실행한다.**  

## **📌 1) 패키지 빌드**
```bash
colcon build --packages-select my_cpp_package
```
📌 **패키지를 빌드하면 실행 파일(`my_node`)이 `install/lib/my_cpp_package/`에 생성된다.**  
📌 빌드 후 `source install/setup.bash` 명령어를 실행하여 패키지를 등록한다.  

```bash
source install/setup.bash
```

---

## **📌 2) ROS2 노드 실행 (`ros2 run`)**
```bash
ros2 run my_cpp_package my_node
```
**📌 실행 결과**
```
[INFO] [my_node]: Hello ROS2! 노드가 실행되었습니다.
```
📌 **ROS2 노드가 성공적으로 실행되었으며, `INFO` 로그가 출력된다.**  

---

# **✅ 5) 실행 중 노드 종료 (`Ctrl+C`)**
> **ROS2 노드는 `rclcpp::spin()`에서 계속 실행된다.**  
> **프로그램을 종료하려면 `Ctrl+C`를 입력한다.**  

**📌 `Ctrl+C` 입력 후 실행 결과**
```
[INFO] [rclcpp]: Shutting down ROS...
```
📌 **ROS2가 정상적으로 종료된다.**  
📌 **노드 종료 시 `rclcpp::shutdown()`이 호출되어 ROS2가 안전하게 종료된다.**  

---

# **📌 정리**
✅ **ROS2 C++ 노드는 `rclcpp::Node`를 상속받아 생성해야 한다.**  
✅ **노드를 실행하려면 `rclcpp::init()`, `rclcpp::spin()`을 사용해야 한다.**  
✅ **CMakeLists.txt에 `add_executable()`을 추가하고, `ament_target_dependencies()`를 설정해야 한다.**  
✅ **패키지를 빌드한 후 `ros2 run my_cpp_package my_node`로 실행할 수 있다.** 🚀  

📌 **다음으로 ROS2 C++ 노드에서 `rclcpp::Publisher`를 사용하여 메시지를 퍼블리시하는 방법을 배워보자!** 🚀


<br>
<br>
<br>
<br>

# **🔹 `auto`, `const`, `struct`의 사용법과 ROS2 코드 예제**
> **목표:**  
> - `auto`, `const`, `struct`의 역할과 활용법을 ROS2 C++ 코드와 함께 익힌다.  
> - ROS2에서의 실제 사용 사례를 통해 이해를 돕는다.  

---

# **✅ 1) `auto` - 자동 타입 추론**
## **📌 `auto`란?**
- **C++11부터 도입된 자동 타입 추론 키워드**  
- **컴파일러가 변수의 타입을 자동으로 결정**  
- **코드를 간결하게 만들고, 복잡한 타입 선언을 줄일 수 있음**  

---

## **🔹 `auto` 기본 사용 예제**
```cpp
auto a = 10;       // int
auto b = 3.14;     // double
auto c = "hello";  // const char*
```
📌 `auto`를 사용하면 **컴파일러가 변수 타입을 자동으로 결정**해준다.  

---

## **🔹 `auto`를 활용한 ROS2 코드 예제**
### **1) `auto`를 이용한 메시지 생성**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/string.hpp"

class AutoExampleNode : public rclcpp::Node {
public:
    AutoExampleNode() : Node("auto_example_node") {
        publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);

        auto message = std_msgs::msg::String();  // ✅ `auto`를 사용하여 메시지 객체 생성
        message.data = "Hello ROS2!";
        publisher_->publish(message);
    }

private:
    rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<AutoExampleNode>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **`auto message = std_msgs::msg::String();`에서 `message`의 타입이 자동으로 결정된다.**  
📌 **코드를 더 간결하게 만들 수 있음.**  

---

### **2) `auto`를 활용한 반복문**
```cpp
std::vector<std::string> topics = {"topic1", "topic2", "topic3"};
for (auto &topic : topics) {  // ✅ `auto`를 사용하여 타입을 자동 추론
    RCLCPP_INFO(this->get_logger(), "토픽: %s", topic.c_str());
}
```
📌 **반복문에서 `auto`를 사용하면 가독성이 좋아지고 유지보수가 쉬워짐.**  

---

# **✅ 2) `const` - 변경 불가능한 값 정의**
## **📌 `const`란?**
- **변수를 상수화(읽기 전용)하여 변경되지 않도록 보호**  
- **포인터, 함수, 클래스 멤버 변수 등 다양한 곳에서 활용**  
- **안정성과 성능을 향상시킴**  

---

## **🔹 `const` 기본 사용 예제**
```cpp
const int a = 10;  // ✅ 변경 불가능한 정수
a = 20;  // ❌ 오류 발생!
```
📌 `const`를 사용하면 **변수의 값을 변경할 수 없음**.  

---

## **🔹 `const`를 활용한 ROS2 코드 예제**
### **1) `const`를 사용하여 변경되지 않는 토픽 이름 정의**
```cpp
const std::string TOPIC_NAME = "sensor_data";  // ✅ 변경 불가능한 상수 선언
auto publisher_ = this->create_publisher<std_msgs::msg::String>(TOPIC_NAME, 10);
```
📌 **토픽 이름이 바뀌지 않도록 `const`를 사용하면 실수를 방지할 수 있음.**  

---

### **2) `const`를 사용한 함수 매개변수**
```cpp
void publish_message(const std::string &msg) {  // ✅ `const`로 원본 보호
    RCLCPP_INFO(this->get_logger(), "메시지: %s", msg.c_str());
}
```
📌 **매개변수를 `const`로 선언하면, 함수 내부에서 변경할 수 없음.**  

---

### **3) `const` 멤버 함수**
```cpp
class SensorNode : public rclcpp::Node {
public:
    SensorNode() : Node("sensor_node") {}

    void get_sensor_info() const {  // ✅ 멤버 변수를 변경하지 않는 함수
        RCLCPP_INFO(this->get_logger(), "센서 정보 조회");
    }
};
```
📌 **멤버 변수를 변경하지 않는 함수는 `const`를 붙이면 안전성이 향상됨.**  

---

### **4) `const`와 포인터 (`const int *`, `int *const`, `const int *const`)**
```cpp
const int *ptr1;  // ✅ 포인터가 가리키는 값 변경 불가능
int *const ptr2 = &a;  // ✅ 포인터 주소 변경 불가능
const int *const ptr3 = &a;  // ✅ 값도 변경 불가능, 포인터도 변경 불가능
```
📌 **포인터의 변경 가능 여부에 따라 `const` 위치가 달라진다.**  

---

# **✅ 3) `struct` - 사용자 정의 데이터 타입**
## **📌 `struct`란?**
- **여러 개의 변수를 하나의 구조체로 묶어서 관리하는 기능**  
- **C++의 `class`와 유사하지만 기본 접근 제한자가 `public`**  
- **ROS2 메시지와 유사한 역할을 할 수 있음**  

---

## **🔹 `struct` 기본 사용 예제**
```cpp
struct SensorData {
    std::string name;
    double value;
};
```
📌 **여러 개의 관련 데이터를 하나의 구조체로 정의할 수 있음.**  

---

## **🔹 `struct`를 활용한 ROS2 코드 예제**
### **1) `struct`를 사용하여 센서 데이터 저장**
```cpp
struct SensorData {
    std::string name;
    double value;
};

void process_sensor_data(const SensorData &data) {
    RCLCPP_INFO(this->get_logger(), "센서 이름: %s, 값: %.2f", data.name.c_str(), data.value);
}
```
📌 **여러 개의 변수를 한 번에 처리할 수 있음.**  

---

### **2) `struct`를 활용한 ROS2 메시지 변환**
```cpp
#include "rclcpp/rclcpp.hpp"
#include "sensor_msgs/msg/temperature.hpp"

struct TemperatureData {
    std::string sensor_name;
    double temperature;
};

class TemperaturePublisher : public rclcpp::Node {
public:
    TemperaturePublisher() : Node("temperature_publisher") {
        publisher_ = this->create_publisher<sensor_msgs::msg::Temperature>("temperature", 10);

        TemperatureData data = {"Sensor_A", 25.5};  // ✅ 구조체 사용
        auto msg = convert_to_ros_message(data);  // ✅ 구조체를 ROS2 메시지로 변환
        publisher_->publish(msg);
    }

private:
    sensor_msgs::msg::Temperature convert_to_ros_message(const TemperatureData &data) {
        sensor_msgs::msg::Temperature msg;
        msg.temperature = data.temperature;
        return msg;
    }

    rclcpp::Publisher<sensor_msgs::msg::Temperature>::SharedPtr publisher_;
};

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<TemperaturePublisher>());
    rclcpp::shutdown();
    return 0;
}
```
📌 **`struct`를 사용하면 센서 데이터를 관리하기 편리하며, ROS2 메시지와 쉽게 변환 가능함.**  

---

# **📌 정리**
| 키워드 | 역할 | 사용 사례 |
|---|---|---|
| **`auto`** | 자동 타입 추론 | 메시지 객체 생성, 반복문 (`for(auto &var : container)`) |
| **`const`** | 변경 불가능한 변수 | 상수 선언, 함수 매개변수 (`const std::string &`), 멤버 함수 (`const`) |
| **`struct`** | 사용자 정의 데이터 타입 | 센서 데이터 관리, ROS2 메시지 변환 |

📌 **이제 `auto`, `const`, `struct`를 활용하여 효율적인 ROS2 C++ 코드를 작성할 수 있다!** 🚀


<br>
<br>

# **🔹 `auto`를 반복문과 변수 선언에서 항상 사용하는 것이 유리한가?**
> **질문:**  
> 1. **`for` 문 같은 반복문에서 항상 `auto`를 사용하는 것이 유리한가?**  
> 2. **처음 타입을 선언할 때 항상 `auto`를 사용하는 것이 유리한가?**  

---

# **✅ 1) 반복문에서 `auto`를 항상 사용하는 것이 유리한가?**
### **📌 일반 `for` 문과 `auto` 사용 비교**
```cpp
std::vector<std::string> topics = {"topic1", "topic2", "topic3"};

for (std::string topic : topics) {  // ✅ 복사 (비효율적)
    std::cout << topic << std::endl;
}

for (const std::string &topic : topics) {  // ✅ 참조 (효율적)
    std::cout << topic << std::endl;
}

for (auto &topic : topics) {  // ✅ `auto` 사용 (가독성 + 효율)
    std::cout << topic << std::endl;
}
```
📌 **`auto`를 사용하면 타입을 직접 선언하지 않아도 되므로 코드가 간결해진다.**  
📌 **하지만, `auto`가 무조건 유리한 것은 아니다.**  

---

### **✅ `auto`가 유리한 경우**
| **상황** | **이유** |
|---|---|
| **타입이 복잡한 경우** | 긴 타입을 생략하여 가독성이 향상됨 |
| **반복문에서 참조를 사용해야 하는 경우** | `auto &`를 사용하면 복사 비용을 줄일 수 있음 |
| **템플릿 코드에서 타입이 유동적인 경우** | `auto`를 사용하면 일반화된 코드 작성 가능 |

```cpp
std::map<std::string, int> data = {{"A", 1}, {"B", 2}};
for (auto &[key, value] : data) {  // ✅ 가독성이 좋음
    std::cout << key << " : " << value << std::endl;
}
```
📌 **`std::map<std::string, int>::iterator`를 직접 쓰면 코드가 길어지므로 `auto`가 유리함.**

---

### **❌ `auto`가 불리한 경우**
| **상황** | **이유** |
|---|---|
| **값이 복사되는지 명확하지 않은 경우** | `auto`를 사용하면 참조(`&`) 여부를 실수할 가능성이 있음 |
| **기본 타입(int, double 등)을 반복문에서 사용** | `auto`가 특별한 이점이 없음 |
| **가독성이 저하되는 경우** | `auto`를 남용하면 코드가 직관적이지 않을 수 있음 |

```cpp
std::vector<int> numbers = {1, 2, 3};

for (auto n : numbers) {  // ✅ 복사 발생 (비효율적)
    n *= 2;  // 원본 데이터 변경되지 않음
}

for (auto &n : numbers) {  // ✅ 참조 사용 (효율적)
    n *= 2;  // 원본 데이터 변경됨
}
```
📌 **`auto`를 사용할 때 참조(`&`)를 붙이지 않으면 복사가 발생할 수 있다.**  

---

## **✅ 2) 변수를 선언할 때 항상 `auto`를 사용하는 것이 유리한가?**
📌 `auto`는 **긴 타입을 단축할 수 있어 유용하지만, 항상 사용하는 것은 좋지 않다.**  

---

### **✅ `auto`가 유리한 경우**
| **상황** | **이유** |
|---|---|
| **타입이 매우 길고 복잡한 경우** | 코드를 간결하게 만듦 |
| **템플릿과 결합하여 사용할 때** | 컴파일러가 적절한 타입을 추론 |
| **반환 타입이 명확하지 않을 때** | STL 컨테이너의 반복자(iterator) 반환값 처리 |

```cpp
auto it = my_map.begin();  // ✅ 반복자 타입이 길어질 때 유리
auto my_function();  // ✅ 반환 타입이 복잡한 함수일 때 유리
```

📌 **반복자(iterator)의 타입이 길어질 때 `auto`를 사용하면 코드가 깔끔해진다.**

---

### **❌ `auto`가 불리한 경우**
| **상황** | **이유** |
|---|---|
| **기본 타입 (`int`, `double`)** | `auto`를 써도 가독성이 향상되지 않음 |
| **명확한 타입이 중요한 경우** | `auto`는 변수의 타입을 숨기므로 코드 이해가 어려울 수 있음 |
| **포인터와 참조를 사용할 때** | `auto`를 쓰면 실수로 값이 복사될 수 있음 |

```cpp
int a = 5;
auto b = a;  // ✅ 문제 없음
auto &c = a;  // ✅ 참조를 사용해야 원본 유지
```
📌 **기본 타입에서는 `auto`를 써도 큰 이점이 없다.**  

---

### **📌 `auto`와 `const auto` 차이**
```cpp
const auto value = 42;  // ✅ value는 변경 불가능한 상수
auto const value2 = 42; // ✅ 동일한 의미
```
📌 **`const auto`를 사용하면 자동 타입 추론 + 값 변경 방지 가능**  

---

## **✅ 결론**
| **상황** | **`auto` 사용 여부** | **이유** |
|---|---|---|
| **복잡한 타입 (`std::map`, `std::vector`의 `iterator`)** | ✅ 사용 | 타입이 길어질 경우 가독성 향상 |
| **기본 타입 (`int`, `double`)** | ❌ 사용 안 함 | 명확한 타입을 사용하는 것이 좋음 |
| **STL 반복문 (`for-each`)** | ✅ 사용 | `auto &`를 사용하면 성능 최적화 가능 |
| **값 복사가 발생할 가능성이 있는 경우** | ⚠️ 주의 | `auto` 대신 `auto &` 또는 `const auto &` 사용 고려 |
| **템플릿 사용 시** | ✅ 사용 | `auto`가 타입 추론을 도와줌 |

📌 **`auto`는 강력한 도구지만, 언제나 최선의 선택은 아니다.** 🚀  
📌 **반복문에서는 `auto &` 또는 `const auto &`를 사용하여 불필요한 복사를 방지하는 것이 중요하다.**  
📌 **기본 타입(`int`, `double`)은 명확성을 위해 `auto`를 사용하지 않는 것이 좋다.**

<br>
<br>
<br>
<br>

# **🔹 5-3. ROS2 퍼블리셔 & 서브스크라이버 (`rclcpp::Publisher`, `rclcpp::Subscription`)**
> **목표:**  
> - **ROS2 C++에서 퍼블리셔(`Publisher`)와 서브스크라이버(`Subscription`)를 구현하는 방법을 익힌다.**  
> - **`rclcpp::QoS` 설정을 활용하여 통신의 신뢰성을 조정하는 방법을 배운다.**  
> - **헤더(`.hpp`)와 소스(`.cpp`)를 분리하여 구조적으로 깔끔한 ROS2 노드를 만든다.**  

---

# **✅ 1) ROS2 퍼블리셔 & 서브스크라이버 개념**
### **📌 1. 퍼블리셔 (`rclcpp::Publisher<T>`)**
- ROS2에서 **토픽을 발행하는 역할**
- **메시지 타입(`T`)을 지정하여 특정 주제로 데이터 전송**
- **QoS(Quality of Service) 설정**을 통해 데이터 전송 방식을 조정 가능

```cpp
rclcpp::Publisher<std_msgs::msg::String>::SharedPtr publisher_;
publisher_ = this->create_publisher<std_msgs::msg::String>("chatter", 10);
```

---

### **📌 2. 서브스크라이버 (`rclcpp::Subscription<T>`)**
- ROS2에서 **토픽을 수신하는 역할**
- **특정 토픽을 구독하여 새로운 메시지를 받으면 콜백 함수 실행**
- **QoS 설정을 통해 수신 방식을 조정 가능**

```cpp
rclcpp::Subscription<std_msgs::msg::String>::SharedPtr subscription_;
subscription_ = this->create_subscription<std_msgs::msg::String>(
    "chatter", 10,
    std::bind(&MyClass::callback_function, this, std::placeholders::_1)
);
```

---

### **📌 3. `rclcpp::QoS` 설정**
QoS(Quality of Service)는 **ROS2에서 데이터 전송 품질을 조정하는 설정**이다.

| **QoS 설정** | **설명** |
|---|---|
| `rclcpp::QoS(10)` | 히스토리 크기가 10인 기본 QoS |
| `rclcpp::QoS(rclcpp::KeepLast(10))` | 최근 10개의 메시지를 유지 (기본값) |
| `rclcpp::QoS(rclcpp::KeepAll())` | 모든 메시지를 유지 (메모리 부담 큼) |
| `rclcpp::QoS(rclcpp::ReliabilityPolicy::Reliable)` | 신뢰성 높은 전송 보장 |
| `rclcpp::QoS(rclcpp::ReliabilityPolicy::BestEffort)` | 가능한 만큼 빠르게 전송 |

---

# **✅ 2) 퍼블리셔 & 서브스크라이버 노드 예제 (헤더 & 소스 분리)**
> **ROS2에서 "센서 데이터"를 퍼블리시하고, 이를 구독하는 노드를 작성한다.**
> - `sensor_publisher.hpp`, `sensor_publisher.cpp`  
> - `sensor_subscriber.hpp`, `sensor_subscriber.cpp`  

---

## **📌 1. 퍼블리셔 노드 (`sensor_publisher`)**
📌 **이 노드는 1초마다 `Float32MultiArray` 메시지를 퍼블리시한다.**  

### **🔹 `sensor_publisher.hpp` (헤더 파일)**
```cpp
#ifndef SENSOR_PUBLISHER_HPP_
#define SENSOR_PUBLISHER_HPP_

#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/float32_multi_array.hpp"

class SensorPublisher : public rclcpp::Node {
public:
    SensorPublisher();

private:
    void publish_data();

    rclcpp::Publisher<std_msgs::msg::Float32MultiArray>::SharedPtr publisher_;
    rclcpp::TimerBase::SharedPtr timer_;
};

#endif  // SENSOR_PUBLISHER_HPP_
```

---

### **🔹 `sensor_publisher.cpp` (소스 파일)**
```cpp
#include "sensor_publisher.hpp"

SensorPublisher::SensorPublisher() : Node("sensor_publisher") {
    // ✅ QoS 설정 (신뢰성 높은 메시지 전송)
    rclcpp::QoS qos_settings(rclcpp::KeepLast(10));
    qos_settings.reliability(RMW_QOS_POLICY_RELIABILITY_RELIABLE);

    publisher_ = this->create_publisher<std_msgs::msg::Float32MultiArray>("sensor_data", qos_settings);

    timer_ = this->create_wall_timer(
        std::chrono::seconds(1),
        std::bind(&SensorPublisher::publish_data, this)
    );
}

void SensorPublisher::publish_data() {
    auto message = std_msgs::msg::Float32MultiArray();
    message.data = {1.1, 2.2, 3.3};  // ✅ 센서 데이터 예제

    RCLCPP_INFO(this->get_logger(), "Publishing: [%.1f, %.1f, %.1f]",
                message.data[0], message.data[1], message.data[2]);

    publisher_->publish(message);
}

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<SensorPublisher>());
    rclcpp::shutdown();
    return 0;
}
```

📌 **이제 퍼블리셔 노드는 `sensor_data` 토픽으로 데이터를 발행한다.**  

---

## **📌 2. 서브스크라이버 노드 (`sensor_subscriber`)**
📌 **이 노드는 `sensor_data` 토픽을 구독하고, 수신된 데이터를 출력한다.**  

### **🔹 `sensor_subscriber.hpp` (헤더 파일)**
```cpp
#ifndef SENSOR_SUBSCRIBER_HPP_
#define SENSOR_SUBSCRIBER_HPP_

#include "rclcpp/rclcpp.hpp"
#include "std_msgs/msg/float32_multi_array.hpp"

class SensorSubscriber : public rclcpp::Node {
public:
    SensorSubscriber();

private:
    void sensor_callback(const std_msgs::msg::Float32MultiArray::SharedPtr msg);

    rclcpp::Subscription<std_msgs::msg::Float32MultiArray>::SharedPtr subscription_;
};

#endif  // SENSOR_SUBSCRIBER_HPP_
```

---

### **🔹 `sensor_subscriber.cpp` (소스 파일)**
```cpp
#include "sensor_subscriber.hpp"

SensorSubscriber::SensorSubscriber() : Node("sensor_subscriber") {
    // ✅ QoS 설정 (Best Effort 모드 사용)
    rclcpp::QoS qos_settings(rclcpp::KeepLast(10));
    qos_settings.reliability(RMW_QOS_POLICY_RELIABILITY_BEST_EFFORT);

    subscription_ = this->create_subscription<std_msgs::msg::Float32MultiArray>(
        "sensor_data", qos_settings,
        std::bind(&SensorSubscriber::sensor_callback, this, std::placeholders::_1)
    );
}

void SensorSubscriber::sensor_callback(const std_msgs::msg::Float32MultiArray::SharedPtr msg) {
    RCLCPP_INFO(this->get_logger(), "Received: [%.1f, %.1f, %.1f]",
                msg->data[0], msg->data[1], msg->data[2]);
}

int main(int argc, char **argv) {
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<SensorSubscriber>());
    rclcpp::shutdown();
    return 0;
}
```

📌 **이제 서브스크라이버 노드는 `sensor_data` 토픽을 구독하고 데이터를 출력한다.**  

---

# **✅ 3) 패키지 빌드 및 실행**
### **📌 패키지 빌드**
```bash
colcon build --packages-select my_cpp_package
source install/setup.bash
```

### **📌 퍼블리셔 실행**
```bash
ros2 run my_cpp_package sensor_publisher
```

### **📌 서브스크라이버 실행**
```bash
ros2 run my_cpp_package sensor_subscriber
```

---

# **📌 정리**
✅ **ROS2에서 `rclcpp::Publisher`를 사용하여 퍼블리셔를 생성하고 `create_publisher()`로 등록한다.**  
✅ **ROS2에서 `rclcpp::Subscription`을 사용하여 서브스크라이버를 생성하고 `create_subscription()`으로 등록한다.**  
✅ **QoS 설정을 활용하여 신뢰성 (`Reliable`)과 속도 (`BestEffort`)를 조정할 수 있다.**  
✅ **코드를 `hpp`와 `cpp`로 분리하여 유지보수성을 높인다.**  

📌 **이제 퍼블리셔 & 서브스크라이버를 활용하여 ROS2에서 센서 데이터를 주고받을 수 있다!** 🚀


<br>
<br>
<br>

# 만약 subscribe 된 msg 를 콜백함수 내부에서 msg data를 변경해야 될 경우는 const 가 아니라 auto 가 들어가는게 맞는가?  

네, 맞습니다! `subscribe`된 메시지(`msg`)의 데이터를 콜백 함수 내부에서 변경하려면, `const`를 제거하고 `auto` 또는 명시적인 타입(`std_msgs::msg::Float32MultiArray::SharedPtr`)을 사용해야 합니다.

---

## **✅ 1) 기본적으로 콜백 함수에서 `msg`는 `const`로 선언되는 이유**
ROS2의 `Subscription` 콜백 함수에서 메시지 데이터는 보통 **읽기 전용**(`const`)으로 선언됩니다.

```cpp
void sensor_callback(const std_msgs::msg::Float32MultiArray::SharedPtr msg)
```
📌 **이렇게 하면 `msg`의 내용을 변경할 수 없음.**  
📌 ROS2에서 같은 메시지를 여러 개의 서브스크라이버가 공유할 수 있기 때문에, 기본적으로 **수정이 불가능한 `const` 포인터**로 전달됩니다.

---

## **✅ 2) 메시지를 변경하려면 `const`를 제거해야 함**
콜백 함수 내부에서 데이터를 변경하려면 `const`를 제거해야 합니다.

### **🔹 `const`를 제거한 버전**
```cpp
void sensor_callback(std_msgs::msg::Float32MultiArray::SharedPtr msg) {
    msg->data[0] += 1.0;  // ✅ 첫 번째 요소 값 변경
    RCLCPP_INFO(this->get_logger(), "Modified Data: [%.1f, %.1f, %.1f]",
                msg->data[0], msg->data[1], msg->data[2]);
}
```
📌 **이제 `msg->data` 값을 변경할 수 있음.**  

---

## **✅ 3) `auto`를 활용한 방법**
### **📌 `auto`를 사용하면 타입을 자동으로 추론 가능**
```cpp
void sensor_callback(auto msg) {
    msg->data[0] += 1.0;
    RCLCPP_INFO(this->get_logger(), "Modified Data: [%.1f, %.1f, %.1f]",
                msg->data[0], msg->data[1], msg->data[2]);
}
```
📌 **여기서 `msg`의 타입은 `std_msgs::msg::Float32MultiArray::SharedPtr`로 자동 추론됨.**  
📌 **하지만, `auto`를 사용하면 코드 가독성이 떨어질 수 있으므로 명확한 타입을 사용하는 것이 더 권장됨.**

---

## **✅ 4) `const`가 필요한 경우와 불필요한 경우**
| **상황** | **적절한 선언 방식** | **이유** |
|---|---|---|
| 메시지를 **읽기만 하는 경우** | `void sensor_callback(const std_msgs::msg::Float32MultiArray::SharedPtr msg)` | 다른 서브스크라이버에서 공유될 수 있으므로 **수정 금지** |
| 메시지를 **변경해야 하는 경우** | `void sensor_callback(std_msgs::msg::Float32MultiArray::SharedPtr msg)` | 데이터 수정 가능 |
| 타입을 **자동 추론하고 싶을 때** | `void sensor_callback(auto msg)` | 가독성은 낮아질 수 있음 |

📌 **일반적으로 `const`를 유지하는 것이 안전하지만, 데이터를 변경해야 한다면 `const`를 제거해야 한다.** 🚀



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


