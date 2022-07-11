# assignment of lidar subscriber
이전까지 간단한 ros publisher 및 subscriber를 만드는 방법에 대해서 배웠습니다. 지금까지 배운 지식을 활용하여
1. lidar 정보가 publish 되고있는 rosbag 파일로부터 python 파일을 실행시켜 lidar 값을 subscribe하고 
2. 읽어온 값을 terminal에 print 해주시면 됩니다. 

## 1. Description
### 1.1. rosbag of lidar information
rosbag 파일은 슬랙에 올려드린 test1.bag 파일을 사용해주세요. rosbag 파일을 실행시키는 방법은 아래와 같습니다. \
roscore 실행 : 
```
roscore
```
새로운 터미널에서 rosbag 실행
```
rosbag play test1.bag
```

### 1.2. lidar ropic
이제 rosbag에서 lidar topic이 publish 되고있습니다. 토픽의 정보는 아래와 같습니다. 
* 토픽명 : /velodye_points 
* 메세지 타입 : sensor_msgs/PointCloud2

### 1.3. Build catkin package 
python 소스코드를 이용하여 catkin package를 빌드하시기 위해서 `lidar_subscriber` 패키지를 만들어야 합니다. 앞서 배운 튜토리얼을 활용하여 catkin_workspace에 패키지를 만들고 빌드해 주세요. \
**Note** : catkin_create_package 할 때 sensor_msgs를 depandancy로 추가해주셔야 합니다.

### 1.4. rviz 에서 라이다 값 확인하기
rosbag에서 나오는 토픽을 rviz에서 확인할 수 있습니다. fixed_frame을 `velodyne`으로 맞춰주시고, 좌측 하단에 add버튼을 눌러서 `Pointcloud2`를 추가해주세요. 그리고 좌측에 추가된 `Pointcloud2`의 토픽을 '/velodyne_points'로 맞춰주시면 lidar 정보를 실시간을 볼 수 있습니다. 이것도 제출해주셔야 해요.

### 1.4. 과제 제출
과제 제출은 slack의 판단팀 채널에 해주시면 됩니다. 제출할 사항은 아래와 같습니다.
1. 사용한 python 파일
2. rviz 에서 lidar 값을 visualize하고, 캡쳐하여 제출
3. lidar data를 terminal 창에 print 한 것을 캡쳐하여 제출

![Screenshot from 2022-07-12 00-46-29](https://user-images.githubusercontent.com/78340346/178304196-d3b3a762-d1ac-47fb-9afd-eb66702b4f9a.png)
![Screenshot from 2022-07-12 00-46-38](https://user-images.githubusercontent.com/78340346/178304213-1c59ccfd-0e76-493c-a1cd-8868ea016246.png)

  


