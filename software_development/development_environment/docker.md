 **Docker 이미지를 온라인 환경에서 다운로드한 후 오프라인 환경에서 실행하는 방법**이 있습니다.  
이를 위해 **docker save / load** 명령어를 사용하면 됩니다.  

---

## **① 온라인 환경에서 Docker 이미지 다운로드 및 저장**
먼저, 인터넷이 연결된 PC에서 필요한 Docker 이미지를 다운로드하고 저장하세요.

### **1. 원하는 Docker 이미지 다운로드**
```bash
docker pull ros:kinetic
```
원하는 ROS 버전의 이미지를 다운로드합니다.  
(예: `ros:kinetic`, `ros:kinetic-ros-base`, `ros:kinetic-xenial` 등)

### **2. 이미지 파일로 저장 (`docker save`)**
```bash
docker save -o ros_kinetic.tar ros:kinetic
```
- `ros_kinetic.tar` 파일로 이미지를 저장합니다.  
- 여러 개의 이미지를 저장할 경우:
  ```bash
  docker save -o ros_images.tar ros:kinetic ros:kinetic-ros-base
  ```

### **3. 저장된 파일을 USB 또는 외장 HDD로 복사**
```bash
cp ros_kinetic.tar /mnt/usb/
```
또는 SCP(Secure Copy) 등을 사용해 오프라인 PC로 파일을 전송할 수도 있습니다.

---

## **② 오프라인 환경에서 Docker 이미지 불러오기**
이제 인터넷이 없는 오프라인 PC에서 Docker 이미지 파일을 불러옵니다.

### **1. 이미지 파일을 오프라인 PC로 이동**
USB, 외장 HDD, SCP 등을 이용해 `ros_kinetic.tar` 파일을 오프라인 PC로 복사합니다.

### **2. Docker 이미지 로드 (`docker load`)**
```bash
docker load -i ros_kinetic.tar
```
- `docker images`를 실행하여 이미지가 정상적으로 로드되었는지 확인하세요.

### **3. 컨테이너 실행**
```bash
docker run -it ros:kinetic bash
```
정상적으로 실행되면 성공입니다!

---

## **추가 옵션: 오프라인 환경에서 컨테이너 생성 및 실행**
만약 여러 개의 컨테이너를 미리 준비하고 싶다면, 오프라인 환경에서도 컨테이너를 내보내고 가져올 수 있습니다.

### **1. 온라인 환경에서 컨테이너 생성 후 저장 (`docker export`)**
```bash
docker run --name my_ros_container ros:kinetic
docker export -o my_ros_container.tar my_ros_container
```

### **2. 오프라인 환경에서 컨테이너 가져오기 (`docker import`)**
```bash
cat my_ros_container.tar | docker import - my_ros_image
docker run -it my_ros_image bash
```

---

## **결론**
**인터넷이 없는 환경에서도 Docker 이미지를 사용하려면 `docker save` / `docker load`를 활용하면 된다!**  
- **`docker save -o <파일명>.tar <이미지>` → 오프라인으로 이동**  
- **`docker load -i <파일명>.tar` → 오프라인 환경에서 불러오기**  
이 방법으로 쉽게 오프라인에서 Docker 환경을 구축할 수 있습니다.
