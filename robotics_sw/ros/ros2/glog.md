 **Google glog**. It is a **C++ logging library** developed by Google, commonly used in large-scale software projects, including **robotics and ROS2 applications**. 

### **Key Features of Google glog**
1. **Logging Levels**: Supports different severity levels:
   - `LOG(INFO)`
   - `LOG(WARNING)`
   - `LOG(ERROR)`
   - `LOG(FATAL)`

2. **Automatic Log File Management**: 
   - By default, logs are written to `/tmp` (Linux/macOS) or `C:\temp` (Windows).
   - Logs are automatically rotated and named based on severity and timestamps.

3. **Thread-Safe Logging**: Suitable for multi-threaded applications.

4. **Stream-like Syntax**: Works similarly to `std::cout`, making it convenient.

5. **Conditional Logging & Verbosity Levels**:
   - `DLOG(INFO) << "Debug info";` (Only active in debug mode)
   - `VLOG(2) << "Verbose logging";` (Verbose levels can be controlled at runtime)

6. **CHECK Macros for Debugging**:
   - `CHECK(condition) << "Message";` (Terminates the program if the condition is false)
   - Variants: `CHECK_EQ(x, y)`, `CHECK_NE(x, y)`, etc.

---

### **How to Use Google glog in ROS2**
If you're developing **ROS2 nodes in C++**, `glog` can be a more structured alternative to `RCLCPP_INFO()`.

#### **1. Install Google glog**
```sh
sudo apt-get install libgoogle-glog-dev
```

#### **2. Add glog to CMakeLists.txt**
```cmake
find_package(glog REQUIRED)
target_link_libraries(your_node glog::glog)
```

#### **3. Basic Usage in a ROS2 Node**
```cpp
#include <rclcpp/rclcpp.hpp>
#include <glog/logging.h>

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("my_node") {
        LOG(INFO) << "ROS2 Node started!";
        LOG(WARNING) << "This is a warning message.";
        LOG(ERROR) << "This is an error message.";

        // Example of CHECK macros
        int x = 10, y = 20;
        CHECK_LT(x, y) << "x should be less than y!";
    }
};

int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();
    return 0;
}
```

---

### **Google glog vs. ROS2 Logging**
| Feature           | Google glog | ROS2 Logging (`rclcpp::Logger`) |
|------------------|------------|--------------------------------|
| Logging Levels  | INFO, WARNING, ERROR, FATAL | DEBUG, INFO, WARN, ERROR, FATAL |
| File Logging    | Yes (by default) | Needs external configuration (`ros2_logging.conf`) |
| Verbose Logging | Yes (`VLOG(n)`) | Yes (`RCUTILS_CONSOLE_OUTPUT_FORMAT`) |
| Thread Safety   | Yes | Yes |
| Custom Formatting | Yes (via `LOG_EVERY_N()`, `LOG_IF()`) | Limited |
| Use in ROS2    | Needs `glog::InitGoogleLogging` | Native |

---

### **When to Use Google glog in ROS2**
✅ If you need **structured logging**, automatic log rotation, or **advanced filtering**.<br>
✅ If you work on **large-scale ROS2 projects** that require detailed debugging beyond `RCLCPP_INFO()`.<br>
✅ If you're **migrating from Google-based frameworks** where `glog` is already used.

🚫 If you need **real-time logging integrated with ROS2 tools**, stick with `RCLCPP_INFO()`.

---


<br>
<br>
<br>
<br>
<br>
<br>

Here are **detailed examples** of using **Google glog in ROS2**. I'll cover various scenarios, including **basic logging, conditional logging, verbosity levels, log filtering, and log file management**.

---

## **1. Install and Configure Google glog in ROS2**
### **Step 1: Install glog**
```sh
sudo apt-get install libgoogle-glog-dev
```

### **Step 2: Add glog to Your ROS2 Package**
Modify your **CMakeLists.txt**:
```cmake
find_package(glog REQUIRED)

add_executable(my_ros2_node src/my_ros2_node.cpp)
target_link_libraries(my_ros2_node glog::glog)
```

Modify **package.xml**:
```xml
<depend>glog</depend>
```

---

## **2. Basic Usage of glog in ROS2**
Create a ROS2 node that logs various messages:
```cpp
#include <rclcpp/rclcpp.hpp>
#include <glog/logging.h>

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("glog_example_node") {
        LOG(INFO) << "ROS2 Node has started!";
        LOG(WARNING) << "This is a warning message.";
        LOG(ERROR) << "An error occurred!";

        int a = 5, b = 10;
        CHECK_LT(a, b) << "a should be less than b!";
    }
};

int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);  // Initialize glog
    FLAGS_logtostderr = 1;  // Log messages to terminal

    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();
    
    google::ShutdownGoogleLogging();  // Cleanup glog
    return 0;
}
```
### **Expected Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] ROS2 Node has started!
W0316 10:00:00.123457 12345 my_ros2_node.cpp:11] This is a warning message.
E0316 10:00:00.123458 12345 my_ros2_node.cpp:12] An error occurred!
```

---

## **3. Logging to Files**
By default, glog stores logs in `/tmp`. You can configure it to store logs in a specific directory.

Modify your **main()** function:
```cpp
int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);

    FLAGS_log_dir = "/home/user/ros2_logs";  // Set log directory
    FLAGS_logtostderr = 0;  // Disable console output
    FLAGS_alsologtostderr = 1;  // Log to both file and terminal

    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();

    google::ShutdownGoogleLogging();
    return 0;
}
```

### **Generated Log Files (Example)**
Logs will be stored in:
```
/home/user/ros2_logs/
  - my_ros2_node.INFO.20250316-100000.log
  - my_ros2_node.WARNING.20250316-100000.log
  - my_ros2_node.ERROR.20250316-100000.log
```

---

## **4. Conditional Logging**
You can log messages based on certain conditions.
```cpp
int x = 5, y = 10;
LOG_IF(INFO, x < y) << "x is smaller than y.";
LOG_IF(ERROR, x > y) << "x is greater than y (this won't be logged).";
```

---

## **5. Verbosity Levels (`VLOG`)**
Google glog supports **verbose logging** using `VLOG(n)`. The higher the `n`, the more detailed the logs.

Modify your **main()** function:
```cpp
int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);

    FLAGS_v = 2;  // Set verbosity level (higher values show more logs)

    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();

    google::ShutdownGoogleLogging();
    return 0;
}
```

In your ROS2 node:
```cpp
VLOG(1) << "Verbose log level 1: This will be shown if FLAGS_v >= 1";
VLOG(2) << "Verbose log level 2: More details (shown if FLAGS_v >= 2)";
VLOG(3) << "Verbose log level 3: Extra details (shown if FLAGS_v >= 3)";
```

Run your node:
```sh
./my_ros2_node --v=2
```
Expected Output:
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Verbose log level 1: This will be shown if FLAGS_v >= 1
I0316 10:00:00.123457 12345 my_ros2_node.cpp:11] Verbose log level 2: More details (shown if FLAGS_v >= 2)
```

---

## **6. Log Only Every N Occurrences**
To prevent log spam:
```cpp
LOG_EVERY_N(INFO, 10) << "This will be logged every 10 occurrences. Count: " << google::COUNTER;
```

Example output (if in a loop):
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:20] This will be logged every 10 occurrences. Count: 10
I0316 10:00:00.223456 12345 my_ros2_node.cpp:20] This will be logged every 10 occurrences. Count: 20
```

---

## **7. Log Only First N Occurrences**
If you want to log something only a few times:
```cpp
LOG_FIRST_N(WARNING, 3) << "This warning appears only the first 3 times!";
```
Expected Output:
```sh
W0316 10:00:00.123456 12345 my_ros2_node.cpp:22] This warning appears only the first 3 times!
W0316 10:00:00.223456 12345 my_ros2_node.cpp:22] This warning appears only the first 3 times!
W0316 10:00:00.323456 12345 my_ros2_node.cpp:22] This warning appears only the first 3 times!
```

---

## **8. Fatal Errors and Assertions**
A `LOG(FATAL)` message will **terminate the program** immediately.
```cpp
LOG(FATAL) << "Critical error! The program will exit.";
```

Using `CHECK`:
```cpp
int a = 5, b = 10;
CHECK_EQ(a, b) << "a and b should be equal!";
```
Expected Output:
```sh
F0316 10:00:00.123456 12345 my_ros2_node.cpp:30] Check failed: a == b: a and b should be equal!
```

---

## **9. Custom Logging Format**
You can modify the logging format with:
```cpp
FLAGS_log_prefix = false;  // Disable default prefix
FLAGS_logbuflevel = -1;  // Flush logs immediately
```

---

## **Conclusion**
Google glog is **powerful for logging in ROS2** with:
✅ **Thread-safe logging** <br>
✅ **File-based log management** <br>
✅ **Conditional, frequency-based, and verbosity-based logging** <br>
✅ **Better debugging with assertions (`CHECK_EQ`)** <br>



<br>
<br>
<br>
<br>
<br>
<br>
<br>


In **Google glog**, you can easily log text messages that include variables using **stream-style syntax (`<<`)**, just like `std::cout`. Here are several examples of how to include variables in your log messages:

---

## **1. Basic Logging with Variables**
```cpp
#include <rclcpp/rclcpp.hpp>
#include <glog/logging.h>

class MyNode : public rclcpp::Node {
public:
    MyNode() : Node("glog_variable_logging") {
        int x = 42;
        double pi = 3.14159;
        std::string name = "ROS2";

        LOG(INFO) << "x = " << x << ", pi = " << pi << ", name = " << name;
    }
};

int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);
    FLAGS_logtostderr = 1;  // Log to console

    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<MyNode>());
    rclcpp::shutdown();

    google::ShutdownGoogleLogging();
    return 0;
}
```
### **Expected Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] x = 42, pi = 3.14159, name = ROS2
```

---

## **2. Logging with Function Calls and Expressions**
You can log **computed values** directly inside `LOG()`:
```cpp
int a = 10, b = 5;
LOG(INFO) << "Sum: " << (a + b) << ", Difference: " << (a - b);
```
### **Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Sum: 15, Difference: 5
```

---

## **3. Logging Vectors and Lists**
If you need to log **collections** (like `std::vector`), you can use a loop or `std::stringstream`:
```cpp
#include <vector>
#include <sstream>

std::vector<int> numbers = {1, 2, 3, 4, 5};
std::stringstream ss;
for (int num : numbers) ss << num << " ";
LOG(INFO) << "Numbers: " << ss.str();
```
### **Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Numbers: 1 2 3 4 5
```

---

## **4. Logging Structures and Objects**
If you have a **custom struct or class**, overload `operator<<` for logging:
```cpp
struct Point {
    double x, y;
    friend std::ostream& operator<<(std::ostream& os, const Point& p) {
        return os << "Point(x=" << p.x << ", y=" << p.y << ")";
    }
};

Point p{3.5, 7.2};
LOG(INFO) << "Position: " << p;
```
### **Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Position: Point(x=3.5, y=7.2)
```

---

## **5. Logging ROS2 Messages (`geometry_msgs::Point`)**
If you're working with **ROS2 message types**, such as `geometry_msgs::Point`, you need a conversion function:
```cpp
#include <geometry_msgs/msg/point.hpp>

std::ostream& operator<<(std::ostream& os, const geometry_msgs::msg::Point& point) {
    return os << "Point(x=" << point.x << ", y=" << point.y << ", z=" << point.z << ")";
}

geometry_msgs::msg::Point point;
point.x = 1.0; point.y = 2.0; point.z = 3.0;
LOG(INFO) << "Robot Position: " << point;
```
### **Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Robot Position: Point(x=1.0, y=2.0, z=3.0)
```

---

## **6. Logging with Conditional Messages**
You can **conditionally log messages** based on variable values:
```cpp
int error_code = 404;
LOG_IF(ERROR, error_code == 404) << "Error: Page not found (404)";
```
### **Output (only if `error_code == 404`)**
```sh
E0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Error: Page not found (404)
```

---

## **7. Logging with Time Stamps**
If you need to log **timestamps**, you can use `std::chrono`:
```cpp
#include <chrono>
#include <ctime>

auto now = std::chrono::system_clock::now();
std::time_t now_c = std::chrono::system_clock::to_time_t(now);
LOG(INFO) << "Current Time: " << std::ctime(&now_c);
```
### **Output**
```sh
I0316 10:00:00.123456 12345 my_ros2_node.cpp:10] Current Time: Sun Mar 16 10:00:00 2025
```

---

## **8. Logging to Specific Files**
If you want logs **only in a specific file**, use `google::SetLogDestination`:
```cpp
google::SetLogDestination(google::INFO, "/home/user/ros2_logs/info.log");
LOG(INFO) << "Logging only to info.log";
```

---

## **9. Using Different Logging Levels Dynamically**
You can **change log levels at runtime**:
```cpp
FLAGS_minloglevel = 2;  // Only WARNING, ERROR, and FATAL messages will be logged
LOG(INFO) << "This won't be logged!";
LOG(WARNING) << "This will be logged!";
LOG(ERROR) << "This is an error message!";
```
### **Output**
```sh
W0316 10:00:00.123456 12345 my_ros2_node.cpp:10] This will be logged!
E0316 10:00:00.123457 12345 my_ros2_node.cpp:11] This is an error message!
```

---

## **Summary**
✅ **Use `LOG(INFO) << "Variable: " << variable;`** to log messages with variables.<br>
✅ **Log containers using `std::stringstream`.**<br>
✅ **Overload `operator<<` for logging custom objects and ROS2 messages.**<br>
✅ **Use `LOG_IF()`, `VLOG()`, and `CHECK()` for conditional logging.**<br>
✅ **Change logging levels dynamically with `FLAGS_minloglevel`.**<br>



<br>
<br>
<br>
<br>
<br>
<br>


### **Google glog with Multi-Threaded Logging in ROS2**
Multi-threaded logging in ROS2 using **Google glog** can be achieved by running **multiple threads** that log messages **concurrently**. Since `glog` is **thread-safe**, it ensures that log messages from different threads do not interfere with each other.

---

## **1. Install and Configure glog for Multi-Threading**
### **Step 1: Install Google glog**
```sh
sudo apt-get install libgoogle-glog-dev
```

### **Step 2: Modify `CMakeLists.txt`**
```cmake
find_package(glog REQUIRED)

add_executable(my_multithreaded_logger src/my_multithreaded_logger.cpp)
target_link_libraries(my_multithreaded_logger glog::glog)
```

### **Step 3: Modify `package.xml`**
```xml
<depend>glog</depend>
```

---

## **2. Multi-Threaded Logging in ROS2 Using glog**
This example:
✅ **Creates a ROS2 Node** running multiple logging threads.<br>
✅ **Uses `std::thread` to simulate logging from multiple sources.**<br>
✅ **Uses `LOG(INFO)`, `LOG(WARNING)`, `LOG(ERROR)` in different threads.**<br>

```cpp
#include <rclcpp/rclcpp.hpp>
#include <glog/logging.h>
#include <thread>
#include <vector>
#include <chrono>

// Function to simulate logging from multiple threads
void logFromThread(int thread_id) {
    for (int i = 0; i < 5; i++) {
        LOG(INFO) << "Thread " << thread_id << " logging iteration " << i;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));  // Simulate work
    }
}

// ROS2 Node with Multi-Threaded Logging
class MultiThreadedLoggerNode : public rclcpp::Node {
public:
    MultiThreadedLoggerNode() : Node("multi_threaded_logger") {
        LOG(INFO) << "Multi-threaded ROS2 Logger Node Started!";

        // Start multiple threads for logging
        for (int i = 0; i < num_threads_; i++) {
            logging_threads_.emplace_back(logFromThread, i);
        }
    }

    ~MultiThreadedLoggerNode() {
        // Join threads before shutdown
        for (auto &t : logging_threads_) {
            if (t.joinable()) {
                t.join();
            }
        }
        LOG(INFO) << "Multi-threaded ROS2 Logger Node Shutting Down!";
    }

private:
    std::vector<std::thread> logging_threads_;
    const int num_threads_ = 4;  // Number of logging threads
};

int main(int argc, char** argv) {
    google::InitGoogleLogging(argv[0]);

    // Configure glog
    FLAGS_logtostderr = 1;  // Log to console
    FLAGS_alsologtostderr = 1;  // Log to both console and file
    FLAGS_log_dir = "/home/user/ros2_logs";  // Set log file directory

    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedLoggerNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();

    google::ShutdownGoogleLogging();
    return 0;
}
```

---

## **3. Expected Multi-Threaded Logging Output**
When running the node, log messages from **multiple threads** will appear simultaneously:
```sh
I0316 10:00:00.123456 12345 my_multithreaded_logger.cpp:15] Multi-threaded ROS2 Logger Node Started!
I0316 10:00:00.123457 12345 my_multithreaded_logger.cpp:8] Thread 0 logging iteration 0
I0316 10:00:00.123458 12345 my_multithreaded_logger.cpp:8] Thread 1 logging iteration 0
I0316 10:00:00.123459 12345 my_multithreaded_logger.cpp:8] Thread 2 logging iteration 0
I0316 10:00:00.123460 12345 my_multithreaded_logger.cpp:8] Thread 3 logging iteration 0
...
I0316 10:00:05.123461 12345 my_multithreaded_logger.cpp:22] Multi-threaded ROS2 Logger Node Shutting Down!
```

---

## **4. Using `std::mutex` to Avoid Log Message Mixing**
Although `glog` is **thread-safe**, you might want to synchronize output to avoid mixed-up logs.

Modify `logFromThread()` to use a **mutex**:
```cpp
#include <mutex>

std::mutex log_mutex;  // Mutex for thread-safe logging

void logFromThread(int thread_id) {
    for (int i = 0; i < 5; i++) {
        {
            std::lock_guard<std::mutex> lock(log_mutex);
            LOG(INFO) << "Thread " << thread_id << " logging iteration " << i;
        }
        std::this_thread::sleep_for(std::chrono::milliseconds(100));  // Simulate work
    }
}
```
Now, log messages will appear in **sequential order**, avoiding overlapping messages.

---

## **5. Using `VLOG(n)` for Thread-Specific Verbose Logging**
`VLOG(n)` allows you to **log messages with different verbosity levels** per thread.
```cpp
void logFromThreadVerbose(int thread_id) {
    for (int i = 0; i < 5; i++) {
        VLOG(1) << "Verbose log from Thread " << thread_id << ", iteration " << i;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
}
```
Run your program with verbosity enabled:
```sh
./my_multithreaded_logger --v=1
```

---

## **6. Logging Errors from Different Threads**
Simulating **error conditions** in multi-threaded logging:
```cpp
void logErrors(int thread_id) {
    for (int i = 0; i < 5; i++) {
        if (i == 3) {
            LOG(ERROR) << "Thread " << thread_id << " encountered an error at iteration " << i;
        }
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
}
```
### **Expected Output**
```sh
E0316 10:00:03.123456 12345 my_multithreaded_logger.cpp:8] Thread 2 encountered an error at iteration 3
```

---

## **7. Log Files for Each Thread**
If you want **separate log files per thread**, modify `logFromThread()`:
```cpp
void logFromThreadToFile(int thread_id) {
    std::string log_filename = "/home/user/ros2_logs/thread_" + std::to_string(thread_id) + ".log";
    google::SetLogDestination(google::INFO, log_filename.c_str());

    for (int i = 0; i < 5; i++) {
        LOG(INFO) << "Thread " << thread_id << " logging iteration " << i;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
}
```
Each thread will generate its own log file:
```
/home/user/ros2_logs/
  - thread_0.log
  - thread_1.log
  - thread_2.log
  - thread_3.log
```

---

## **Conclusion**
🔹 **Multi-threaded logging in ROS2 with `glog` is thread-safe**<br>
🔹 **Use `std::mutex` if you want logs to appear sequentially**<br>
🔹 **Use `VLOG(n)` for per-thread verbosity control**<br>
🔹 **Separate log files can be created per thread**<br>




<br>
<br>
<br>
<br>
<br>
<br>
<br>

### **gflags: Google Command-Line Flag Library**
**gflags**는 Google에서 개발한 **C++ 기반의 커맨드라인 플래그(옵션) 라이브러리**입니다.  
즉, 프로그램 실행 시 **명령줄 인자를 쉽게 관리하고 파싱할 수 있도록 도와주는 라이브러리**입니다.

#### **🔥 주요 특징**
✅ `--flag=value` 형식으로 커맨드라인에서 인자 전달 가능  
✅ **전역 변수**로 관리되므로 어디서든 접근 가능  
✅ 기본값 설정 가능 (`DEFINE_int32`, `DEFINE_bool`, `DEFINE_double`, `DEFINE_string` 등)  
✅ **glog와 함께 사용하면 강력한 디버깅 및 로깅 환경 구축 가능**  

---

## **1. gflags 설치 방법**
Ubuntu에서 gflags를 설치하려면:
```sh
sudo apt-get install libgflags-dev
```

### **CMake 설정**
`CMakeLists.txt`에서 `gflags`를 추가:
```cmake
find_package(gflags REQUIRED)

add_executable(my_program src/my_program.cpp)
target_link_libraries(my_program gflags)
```

`package.xml`에도 `gflags` 추가:
```xml
<depend>gflags</depend>
```

---

## **2. gflags 기본 사용법**
### **코드 예제**
```cpp
#include <iostream>
#include <gflags/gflags.h>

// Define command-line flags
DEFINE_bool(debug, false, "Enable debug mode");
DEFINE_int32(port, 8080, "Port number for the server");
DEFINE_string(config, "default.yaml", "Path to config file");

int main(int argc, char** argv) {
    // Parse command-line flags
    gflags::ParseCommandLineFlags(&argc, &argv, true);

    // Use flags in the program
    std::cout << "Debug mode: " << (FLAGS_debug ? "ON" : "OFF") << std::endl;
    std::cout << "Server running on port: " << FLAGS_port << std::endl;
    std::cout << "Using config file: " << FLAGS_config << std::endl;

    return 0;
}
```

---

### **3. 실행 예제**
컴파일 후 실행할 때 커맨드라인에서 값을 지정할 수 있음:
```sh
./my_program --debug=true --port=5000 --config="robot.yaml"
```
출력 결과:
```sh
Debug mode: ON
Server running on port: 5000
Using config file: robot.yaml
```
만약 `--debug`, `--port`, `--config` 플래그를 지정하지 않으면 **기본값**이 사용됨.

---

## **4. ROS2에서 gflags와 glog 함께 사용하기**
**ROS2 노드에서 `gflags`를 이용해 플래그를 설정하고, `glog`를 이용해 로깅**하는 예제:

```cpp
#include <rclcpp/rclcpp.hpp>
#include <gflags/gflags.h>
#include <glog/logging.h>

// Define command-line flags
DEFINE_bool(enable_logging, true, "Enable glog logging");
DEFINE_string(log_dir, "/home/user/ros2_logs", "Directory to save logs");
DEFINE_int32(logging_level, 0, "Logging verbosity level");

class MyROS2Node : public rclcpp::Node {
public:
    MyROS2Node() : Node("gflags_glog_example") {
        if (FLAGS_enable_logging) {
            google::InitGoogleLogging(this->get_name());
            FLAGS_log_dir = FLAGS_log_dir;
            FLAGS_v = FLAGS_logging_level;
        }

        LOG(INFO) << "ROS2 Node Started!";
    }

    ~MyROS2Node() {
        if (FLAGS_enable_logging) {
            google::ShutdownGoogleLogging();
        }
    }
};

int main(int argc, char** argv) {
    gflags::ParseCommandLineFlags(&argc, &argv, true);
    rclcpp::init(argc, argv);

    auto node = std::make_shared<MyROS2Node>();
    rclcpp::spin(node);
    rclcpp::shutdown();

    return 0;
}
```

---

### **5. 실행 예제**
```sh
./gflags_glog_example --enable_logging=true --log_dir="/tmp/logs" --logging_level=1
```

📌 `FLAGS_enable_logging`이 `true`일 경우, `glog`를 활성화하여 **로그를 특정 폴더에 저장**하고, `FLAGS_logging_level`을 사용해 **로그 세부 정보 조절** 가능.

---

## **6. gflags + glog + 멀티스레드 예제**
### **여러 개의 스레드에서 gflags 값에 접근하는 로깅 시스템**
```cpp
#include <rclcpp/rclcpp.hpp>
#include <gflags/gflags.h>
#include <glog/logging.h>
#include <thread>
#include <vector>

// Define command-line flags
DEFINE_int32(num_threads, 4, "Number of logging threads");

void logFromThread(int thread_id) {
    for (int i = 0; i < 5; i++) {
        LOG(INFO) << "Thread " << thread_id << " logging iteration " << i;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
}

class MultiThreadedLoggerNode : public rclcpp::Node {
public:
    MultiThreadedLoggerNode() : Node("multi_threaded_logger") {
        LOG(INFO) << "Starting multi-threaded logger with " << FLAGS_num_threads << " threads.";

        for (int i = 0; i < FLAGS_num_threads; i++) {
            threads_.emplace_back(logFromThread, i);
        }
    }

    ~MultiThreadedLoggerNode() {
        for (auto &t : threads_) {
            if (t.joinable()) t.join();
        }
        LOG(INFO) << "Multi-threaded logger shutting down!";
    }

private:
    std::vector<std::thread> threads_;
};

int main(int argc, char** argv) {
    gflags::ParseCommandLineFlags(&argc, &argv, true);
    google::InitGoogleLogging(argv[0]);
    FLAGS_logtostderr = 1;

    rclcpp::init(argc, argv);
    auto node = std::make_shared<MultiThreadedLoggerNode>();
    rclcpp::spin(node);
    rclcpp::shutdown();

    google::ShutdownGoogleLogging();
    return 0;
}
```

### **실행 예제**
```sh
./multi_threaded_logger --num_threads=6
```
**출력 예시:**
```sh
I0316 10:00:00.123456 12345 multi_threaded_logger.cpp:10] Starting multi-threaded logger with 6 threads.
I0316 10:00:00.123457 12345 multi_threaded_logger.cpp:8] Thread 0 logging iteration 0
I0316 10:00:00.123458 12345 multi_threaded_logger.cpp:8] Thread 1 logging iteration 0
...
I0316 10:00:05.123459 12345 multi_threaded_logger.cpp:22] Multi-threaded logger shutting down!
```

---

## **📌 gflags + glog 정리**
| **기능** | **gflags** | **glog** |
|----------|-----------|----------|
| 목적 | 커맨드라인 인자 관리 | 로그 기록 |
| 변수 타입 | `bool`, `int`, `double`, `string` | 문자열 기반 로그 메시지 |
| 설정 방법 | `DEFINE_*` 매크로 사용 | `LOG(INFO)`, `LOG(ERROR)` 사용 |
| 실행 시 변경 가능 여부 | ✅ 가능 (`--flag=value`) | ❌ (설정 파일 또는 코드에서 변경 필요) |
| 사용 예시 | `--num_threads=4` | `LOG(INFO) << "Hello, ROS2!"` |

---

## **마무리**
✅ `gflags`는 **ROS2 프로그램에서 커맨드라인 인자를 쉽게 관리할 수 있도록 도와주는 라이브러리**  
✅ `glog`와 함께 사용하면 **로깅을 제어할 수 있어 강력한 디버깅 환경 구축 가능**  
✅ `gflags::ParseCommandLineFlags(&argc, &argv, true);` 호출하여 명령줄 플래그를 초기화  
✅ `FLAGS_변수이름`을 통해 코드 내에서 직접 사용 가능  

이제 `gflags`와 `glog`를 활용하여 **강력한 ROS2 로깅 시스템**을 구축할 수 있음! 🚀  
