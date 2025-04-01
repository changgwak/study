https://robbyrobotics.notion.site/152cc9fed94181cb92d7fba14cbec60c

# 시뮬레이션 환경 구성

# 사용할 로봇 소개

---

## ADLINK **Technology**

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/431e5427-3bd2-4679-b53c-cd3e728798b6/Untitled.png)

- **ADLINK Technology Inc.**는 대만에 본사를 둔 글로벌 기업으로, 1995년에 설립되었습니다. 이 회사는 산업 자동화, 통신, 의료, 교통 및 방위 산업 등 다양한 산업 분야에서 사용되는 고성능 임베디드 컴퓨팅 제품을 개발하는 것으로 잘 알려져 있습니다.
- 로봇 사업에서 특히 자율 이동 로봇(AMR)과 관련된 첨단 기술을 개발하고 있습니다. 이 회사는 로봇 운영 시스템인 ROS 2를 기반으로 한 다양한 로봇 제어 솔루션을 제공하며, 이를 통해 산업 자동화 및 다양한 산업 환경에서의 솔루션을 제공하고 있습니다.
    - [ADLINK의 ROS2 관련 솔루션](https://www.adlinktech.com/en/ROS2-Solution)
        
        ![Solution Stack](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/ccf0dd74-213e-47ee-ba68-e53b00550fa1/Untitled.png)
        
        Solution Stack
        

## NeuronBot

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/04e3b1ff-23b2-4a79-9eca-fdd8af3c50d3/Untitled.png)

- 빠른 로봇 개발을 위한 ROS/ROS2 기반의 로봇
    
    [NeuronBot Datasheet.pdf](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/884ac28c-d11f-4023-8fad-d4fe48bbc999/NeuronBot_Datasheet.pdf)
    
    [NeuronBot Manual.pdf](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/1d7a5446-277f-4b01-a0da-20dbc285c231/NeuronBot_Manual.pdf)
    

## 로봇 시뮬레이션 환경 구성 및 설치

1. 환경 구성을 위해 필요한 요소들을 설치합니다.
    
    ```bash
    sudo apt update && sudo apt install -y \
      build-essential \
      cmake \
      git \
      libbullet-dev \
      python3-colcon-common-extensions \
      python3-flake8 \
      python3-pip \
      python3-pytest-cov \
      python3-rosdep \
      python3-setuptools \
      python3-vcstool \
      openssh-server \
      wget
    ```
    
2. 워크스페이스를 구성하고 필요한 리소스들을 가져옵니다.
    
    ```bash
    mkdir -p ~/nav2_ws/src
    cd ~/nav2_ws/
    wget https://raw.githubusercontent.com/Adlink-ROS/neuronbot2_ros2.repos/humble/neuronbot2_ros2.repos
    vcs import src < neuronbot2_ros2.repos
    ```
    
3. 워크스페이스 안의 모든 의존성 패키지들을 설치합니다.
    
    ```bash
    cd ~/nav2_ws/
    rosdep update
    rosdep install --from-paths src --ignore-src -r -y --rosdistro humble
    ```
    
4. 워크스페이스 내 패키지들을 빌드합니다.
    
    ```bash
    cd ~/nav2_ws/
    colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
    
    source ~/nav2_ws/install/local_setup.bash # 또는 새 터미널 열기
    ```
    
    - `.bashrc` 또는 `.zshrc`에서 워크스페이스를 이미 등록하였습니다.

## 시뮬레이션 환경 열기 및 간단한 제어

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/221feab7-e97a-4f24-9755-7783912f72d8/Untitled.png)

1. 아래 두 환경 중 원하는 환경을 열어줍니다.
    
    ```bash
    ros2 launch neuronbot2_gazebo neuronbot2_world.launch.py
    ```
    
    - `neuronbot2_world.launch.py`의 28번째 줄의 파일을 수정하여 world를 바꿀 수 있습니다.
    - **Mememan world** (`mememan_world.model`)
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/141d0c5e-0358-45d6-ba76-247d5565b1f5/Untitled.png)
        
    - **Phenix world** (`phenix_world.model`)
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/8ed28739-9f65-4409-8182-3f7d7aa07ee0/Untitled.png)
        
2. 아래 명령어를 통해 로봇을 제어해 볼 수 있습니다.
    
    ```bash
    ros2 run teleop_twist_keyboard teleop_twist_keyboard
    ```
    
    ![teleop.gif](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/6705b24f-59e4-4c42-9b3a-1ddd7c7d4d8e/teleop.gif)
    

## Troubleshooting

### 문제점

- 아래와 같은 에러 메시지와 함께 gazebo가 켜지지 않는 경우
    
    ```
    [gzclient-2] gzclient: /usr/include/boost/smart_ptr/shared_ptr.hpp:728: typename boost::detail::sp_member_access<T>::type boost::shared_ptr<T>::operator->() const [with T = gazebo::rendering::Camera; typename boost::detail::sp_member_access<T>::type = gazebo::rendering::Camera*]: Assertion `px != 0' failed.
    [ERROR] [gzclient-2]: process has died [pid 12360, exit code -6, cmd 'gzclient'].
    ```
    

### 해결책

- `~/.bashrc` 또는 `~/.zshrc` 아래 환경변수 추가
    
    ```bash
    export GAZEBO_RESOURCE_PATH=/usr/share/gazebo-11
    ```
    
    - 본인 PC에 설치된 Gazebo 환경에 맞춰 경로를 정의해줘야 함
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/c923460b-7545-467c-b833-23976a576f85/Untitled.png)
