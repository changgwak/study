Setting up a **C++ development environment** on **VSCode** in **Ubuntu** involves installing the necessary tools, configuring the **C++ compiler**, and setting up a **build system**. Here’s a step-by-step guide:

---

## **Step 1: Install Required Packages**
First, you need a **C++ compiler** and **build tools**.

### Install GCC and G++:
```bash
sudo apt update
sudo apt install build-essential
```
This installs:
- **g++ (GNU Compiler Collection for C++)**
- **make (build system)**
- **other essential development tools**

### Install CMake (Optional, but recommended for larger projects):
```bash
sudo apt install cmake
```

---

## **Step 2: Install VSCode and C++ Extensions**
### If you haven't installed VSCode yet, install it via snap:
```bash
sudo snap install --classic code
```

### Open VSCode and install the following extensions:
1. **C/C++** (by Microsoft) – Provides IntelliSense, debugging, and code formatting.
2. **CMake Tools** (optional) – If using CMake as a build system.

---

## **Step 3: Create a C++ Source File**
Create a project folder:
```bash
mkdir cpp_project && cd cpp_project
code .
```

Inside VSCode, create a new file `main.cpp`:
```cpp
#include <iostream>

int main() {
    std::cout << "Hello, VSCode!" << std::endl;
    return 0;
}
```

---

## **Step 4: Compile and Run C++ Code**
### **Method 1: Compile Manually Using g++**
Open the terminal inside VSCode (`Ctrl + ~`) and run:
```bash
g++ -o main main.cpp
./main
```

---

## **Step 5: Configure Build Tasks (Automate Compilation)**
To automate the build process, you can create a **tasks.json** file.

1. Open **Command Palette** (`Ctrl + Shift + P`), then type:
   ```
   Tasks: Configure Task
   ```
   Select **"Create tasks.json file from template"** → Choose **"Others"**.

2. Replace the generated `tasks.json` (`.vscode/tasks.json`) with:
   ```json
   {
       "version": "2.0.0",
       "tasks": [
           {
               "label": "Build C++",
               "type": "shell",
               "command": "g++",
               "args": [
                   "-g",
                   "main.cpp",
                   "-o",
                   "main"
               ],
               "group": {
                   "kind": "build",
                   "isDefault": true
               }
           }
       ]
   }
   ```
3. Now, build your C++ program by pressing:
   ```
   Ctrl + Shift + B
   ```
   This compiles `main.cpp` into an executable `main`.

---

## **Step 6: Configure Debugging**
For debugging, create a `.vscode/launch.json` file.

1. Open **Command Palette** (`Ctrl + Shift + P`) and select:
   ```
   Debug: Open launch.json
   ```
   Choose **C++ (GDB/LLDB)**.

2. Replace the generated `launch.json` with:
   ```json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "Debug C++",
               "type": "cppdbg",
               "request": "launch",
               "program": "${workspaceFolder}/main",
               "args": [],
               "stopAtEntry": false,
               "cwd": "${workspaceFolder}",
               "environment": [],
               "externalConsole": false,
               "MIMode": "gdb",
               "setupCommands": [
                   {
                       "description": "Enable pretty-printing",
                       "text": "-enable-pretty-printing",
                       "ignoreFailures": true
                   }
               ],
               "preLaunchTask": "Build C++"
           }
       ]
   }
   ```

3. **Run Debugging**:
   - Set breakpoints in **main.cpp**.
   - Press `F5` to start debugging.

---

## **Step 7: (Optional) Configure CMake for Large Projects**
If you’re using **CMake**, create a `CMakeLists.txt` file:
```cmake
cmake_minimum_required(VERSION 3.10)
project(MyProject)

set(CMAKE_CXX_STANDARD 17)

add_executable(main main.cpp)
```

To build:
```bash
mkdir build && cd build
cmake ..
make
./main
```

---

### **Conclusion**
Now, you can **write, compile, build, and debug** C++ code efficiently in VSCode on Ubuntu. 🎯


<br>
<br>
<br>
<br>
<br>
<br>
<br>


You can check or change the **C++ version** used for compiling your code in VSCode by specifying the **C++ standard flag** in `g++` or `CMake`. Here's how:

---

## **1. Check the Installed GCC Version**
Before setting the C++ standard, check which version of **GCC** you have installed:
```bash
g++ --version
```
You will see something like:
```
g++ (Ubuntu 11.3.0-1ubuntu1~22.04) 11.3.0
```
- **GCC 11+** supports C++20.
- **GCC 12+** supports experimental C++23 features.

If you need a newer version, install it with:
```bash
sudo apt install g++-12
```
Then, check available versions:
```bash
update-alternatives --query g++
```
And switch versions if needed:
```bash
sudo update-alternatives --config g++
```

---

## **2. Specify the C++ Standard in `g++` Compilation**
By default, `g++` compiles with an older C++ standard. You can **specify** the version explicitly.

### **Example Commands**
- **C++11**:
  ```bash
  g++ -std=c++11 -o main main.cpp
  ```
- **C++14**:
  ```bash
  g++ -std=c++14 -o main main.cpp
  ```
- **C++17**:
  ```bash
  g++ -std=c++17 -o main main.cpp
  ```
- **C++20**:
  ```bash
  g++ -std=c++20 -o main main.cpp
  ```
- **C++23** (if supported by GCC):
  ```bash
  g++ -std=c++23 -o main main.cpp
  ```

If the compiler doesn’t support a specific standard, it will show an error.

---

## **3. Change the C++ Version in `tasks.json` (VSCode)**
If you use VSCode's **tasks.json** for automated builds, modify it like this:

```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Build C++20",
            "type": "shell",
            "command": "g++",
            "args": [
                "-std=c++20",
                "-g",
                "main.cpp",
                "-o",
                "main"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
```

Then, build your project by pressing:
```
Ctrl + Shift + B
```

---

## **4. Change C++ Version in CMake**
If you use **CMake**, specify the C++ version in `CMakeLists.txt`:

```cmake
cmake_minimum_required(VERSION 3.10)
project(MyProject)

set(CMAKE_CXX_STANDARD 20)   # Change to 11, 14, 17, 20, 23, etc.
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(main main.cpp)
```

Then, build your project:
```bash
mkdir build && cd build
cmake ..
make
./main
```

---

## **5. Verify the C++ Standard in Your Code**
If you want to **print the C++ version** in your program:
```cpp
#include <iostream>

int main() {
    std::cout << "C++ version: " << __cplusplus << std::endl;
    return 0;
}
```

Expected Output:
- `201103L` → C++11
- `201402L` → C++14
- `201703L` → C++17
- `202002L` → C++20

---

## **Summary**
| Method | How to Change C++ Version |
|--------|---------------------------|
| **g++ Compiler** | `g++ -std=c++20 -o main main.cpp` |
| **VSCode `tasks.json`** | Add `"-std=c++20"` in `"args"` |
| **CMake** | `set(CMAKE_CXX_STANDARD 20)` |
| **Check Version in Code** | Print `__cplusplus` |

Now, you can **compile with any C++ version** in VSCode on Ubuntu! 🚀  
