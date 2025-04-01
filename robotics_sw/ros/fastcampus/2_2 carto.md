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


      <br>
      <br>
      <br>

      # Cartographer SLAM

# Cartographer 수행을 위한 준비

---

## Launch 파일

- `~/nav2_ws/src/neuronbot2/neuronbot2_slam/launch/cartographer_launch.py`에서 **cartographer_ros** 패키지의 두 가지 노드가 사용되었습니다.
    
    ```python
    ...
    
    Node(
        package='cartographer_ros',
        executable='**cartographer_node**',
        name='cartographer_node',
        output='screen',
        parameters=[{'use_sim_time': use_sim_time}],
        arguments=[
            '-configuration_directory', cartographer_config_dir,
            '-configuration_basename', configuration_basename]),
    
    Node(
        package='cartographer_ros',
        executable='**cartographer_occupancy_grid_node**',
        name='occupancy_grid_node',
        output='screen',
        parameters=[{'use_sim_time': use_sim_time}],
        arguments=['-resolution', resolution, '-publish_period_sec', publish_period_sec]),
    
    ...
    
    ```
    
    - **cartographer_node**의 arguments로 설정 파일의 경로(`-configuration_directory`)와 설정 파일의 이름(`-configuration_basename`) 포함되어야하기 때문에 아래 코드와 같이 사전에 정의를 해놓았습니다.
        
        ```python
        cartographer_config_dir = LaunchConfiguration('cartographer_config_dir', 
            default=os.path.join(get_package_share_directory('neuronbot2_slam') , 'config'))
        configuration_basename = LaunchConfiguration('configuration_basename', default='cartographer.lua')
        ```
        

## Lua 파일

- 위에서 언급된 경로(`~/nav2_ws/src/neuronbot2/neuronbot2_slam/config`)에는 `cartographer.lua` 파일이 있습니다.
    
    ```lua
    include "map_builder.lua"
    include "trajectory_builder.lua"
    
    options = {
        map_builder = MAP_BUILDER,
        trajectory_builder = TRAJECTORY_BUILDER,
        map_frame = "map",
        tracking_frame = "base_link",
        published_frame = "odom",
        odom_frame = "odom",
        provide_odom_frame = false,
        publish_frame_projected_to_2d = true,
        use_odometry = true,
        use_nav_sat = false,
        use_landmarks = false,
        num_laser_scans = 1,
        num_multi_echo_laser_scans = 0,
        num_subdivisions_per_laser_scan = 1,
        num_point_clouds = 0,
    
    ...
    ```
    
    - 각 설정에 대해서는 파라미터 튜닝 파트에서 알아보도록 하겠습니다.

## Rviz 파일

- TF, 2D LiDAR 데이터, Map 시각화를 위해 아래와 같이 적절히 설정해주고 저장합니다.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/bd34e57e-0cf1-43b7-9735-5a19dcebf829/Untitled.png)
    
    - 실습에서는 사전에 저장해놓은 `~/nav2_ws/src/neuronbot2/neuronbot2_slam/rviz` 경로의 `slam.rviz` 파일을 사용할 것 입니다.

# Mapping 실습

---

## 실습 환경 구성

1. 아래 명령어를 통해 시뮬레이션 환경을 내려받습니다.
    
    ```bash
    cd ~/nav2_ws/src
    git clone https://github.com/aws-robotics/aws-robomaker-bookstore-world.git -b ros2
    ```
    
2. 내려받은 `aws_robomaker_bookstore_world` 패키지만 따로 빌드해줍니다.
    
    ```bash
    cd ~/nav2_ws
    colcon build --symlink-install --packages-select aws_robomaker_bookstore_world
    ```
    
3. 새 터미널을 열고 시뮬레이션 환경이 잘 열리는지 확인합니다.
    
    ```bash
    ros2 launch aws_robomaker_bookstore_world view_bookstore.launch.py
    ```
    
    ![AWS RoboMaker Bookstore World](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/b9a7fb12-6f67-41a7-85ce-b73b32abf0d7/Untitled.png)
    
    AWS RoboMaker Bookstore World
    

## Troubleshooting

### 문제점

- 아래와 같은 에러 메시지와 함께 gazebo가 켜지지 않는 경우
    
    ```
    [gzclient-2] gzclient: /usr/include/boost/smart_ptr/shared_ptr.hpp:728: typename boost::detail::sp_member_access<T>::type boost::shared_ptr<T>::operator->() const [with T = gazebo::rendering::Camera; typename boost::detail::sp_member_access<T>::type = gazebo::rendering::Camera*]: Assertion `px != 0' failed.
    [INFO] [spawn_entity.py-4]: process has finished cleanly [pid 37848]
    [ERROR] [gzclient-2]: process has died [pid 37844, exit code -6, cmd 'gzclient'].
    ```
    

### 해결책

- 사용하는 환경에 맞게 `~/.bashrc` 또는 `~/.zshrc`에 아래 환경변수 추가
    
    ```bash
    export GAZEBO_RESOURCE_PATH=/usr/share/gazebo-11
    ```
    
    - 본인 PC에 설치된 Gazebo 환경에 맞춰 경로를 정의해줘야 함
        
        ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/c923460b-7545-467c-b833-23976a576f85/Untitled.png)
        

## 시뮬레이션 환경에 neuronbot2을 spawn하기

1. `~/nav2_ws/src/neuronbot2/neuronbot2_gazebo/launch/` 경로의 `neuronbot2_world.launch.py` 파일을 일부 수정해줍니다.
    
    ```python
    ...
    
    def generate_launch_description():
    		launch_file_dir = os.path.join(get_package_share_directory('neuronbot2_gazebo'), 'launch')
    		pkg_gazebo_ros = get_package_share_directory('gazebo_ros')
    		
    		gazebo_model_path = os.path.join(get_package_share_directory('neuronbot2_gazebo'), 'models')
    		**world_model_path = os.path.join(get_package_share_directory('aws_robomaker_bookstore_world'), 'models')**
    		
    		if 'GAZEBO_MODEL_PATH' in os.environ:
    		    **os.environ['GAZEBO_MODEL_PATH'] += ":" + gazebo_model_path + ":" + world_model_path**
    		else :
    		    os.environ['GAZEBO_MODEL_PATH'] = gazebo_model_path
    		
    		use_sim_time = LaunchConfiguration('use_sim_time', default='true')
    		use_camera = LaunchConfiguration('use_camera', default='none')
    		x_pose = LaunchConfiguration('x_pose', default='0.0')
    		y_pose = LaunchConfiguration('y_pose', default='0.0')
    		
    		world = os.path.join(
    		    **get_package_share_directory('aws_robomaker_bookstore_world'),**
    		    'worlds',
    		    **'bookstore.world'**
    		)
    
    ...
    ```
    
    - **`aws_robomaker_bookstore_world`** 패키지의 `models` 디렉토리 안에 있는 모델들을 Gazebo가 읽을 수 있도록 환경변수에 추가해주었습니다.
        
        ```python
        **world_model_path = os.path.join(get_package_share_directory('aws_robomaker_bookstore_world'), 'models')**
        
        if 'GAZEBO_MODEL_PATH' in os.environ:
            **os.environ['GAZEBO_MODEL_PATH'] += ":" + gazebo_model_path + ":" + world_model_path**
        else :
            os.environ['GAZEBO_MODEL_PATH'] = gazebo_model_path
        ```
        
    - 일부 함수들을 활용해 월드 파일이 있는 경로를 수정해줬습니다.
        
        ```python
        world = os.path.join(
            **get_package_share_directory('aws_robomaker_bookstore_world'),**
            'worlds',
            **'bookstore.world'**
        )
        ```
        
2. **neuronbot2**가 `bookstore.world`에 잘 spawn되는지 아래 명령어를 통해 확인합니다.
    
    ```bash
    ros2 launch neuronbot2_gazebo neuronbot2_world.launch.py
    ```
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/427ef1fd-47e5-4eb2-ae6c-a60c46064bde/Untitled.png)
    

## Cartographer를 통한 SLAM 수행

1. 아래 명령어를 통해 Mapping을 수행할 수 있습니다.
    
    ```bash
    ros2 launch neuronbot2_slam cartographer_launch.py open_rviz:=true use_sim_time:=true
    ```
    
2. 터미널을 추가로 열어 아래 노드를 실행시키고 지도를 작성합니다.
    
    ```bash
    ros2 run teleop_twist_keyboard teleop_twist_keyboard
    ```
    
    ![mapping.gif](https://prod-files-secure.s3.us-west-2.amazonaws.com/165a18af-9d8a-4762-809c-e48f1e13d66d/0a04168d-aa3c-4425-9af9-1c2cf34af2e1/mapping.gif)
