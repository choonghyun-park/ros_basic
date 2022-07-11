# creating node and simple publisher

## 1. Make workspace and create package
```
mkdir -p ~/simpleros_ws/src
cd ~/simpleros_ws
catkin_make
cd ~/simpleros_ws/src
catkin_create_pkg beginner_tutorials rospy std_msgs 
```
## 2. Make scipts directory
Create the scripts directory in beginner_tutorials package
```
cd ~/simpleros_ws/src/beginner_tutorials
mkdir scripts
```
## 3. Create source code of simple publisher and give permission using chmod
Please create talker.py in `scripts` directory.
```
cd ~/simpleros_ws/src/beginner_tutorials/scripts
```
The contents of talker.py is [here](https://github.com/choonghyun-park/ros_basic/blob/main/1.%20Simple%20publisher%20and%20subscriber/talker.py)\
Give permission
```
chmod +x talker.py
```
## 4. Add the above line to CMakeLists.txt
```python
catkin_install_python(PROGRAMS scripts/talker.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
```

## 5. Build the workspace using `catkin_make`
```
cd ~/simpleros_ws
catkin_make
```

## 6. launch
```
rosrun beginner_tutorials talker.py
```


