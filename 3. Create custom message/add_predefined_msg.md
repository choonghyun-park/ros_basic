# Add predefined msg
This is the tutorial of add the pre-defined msg.\
You can use the ros message format which is already defined in ros dependancy module. For example a message module `std_msgs` has message format of 
`string`, `int`, `float`, `time`, etc. Any other pre-defined message type can be `nav_msgs`, `sensor_msgs` and something else. So, you can use this 
msg format by simple workflow in below.

## 1. Include the dependant module while catkin_create_pkg
When you create the new package, you will use the below command:
```
catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
```
By add the dependancy, (for example std_msgs) you can use the ros pre-defined msg format.\
If you need dependancy of `std_msgs` :
```
catkin_create_pkg beginner_tutorials rospy std_msgs
```

## 2. Add msg after create package
If you want to add the using msg format after create your own package, you have to add the below blocks of code.\
Description environment :
* Package name : beginner_tutorials
* dependancy : rospy, std_msgs
* added message : sensor_msgs 
To add the `sensor_msgs` in `beginner_tutorials` package, check out below blocks of code.

### 2.1. CMakeLists.txt
```
find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  sensor_msgs
)

generate_messages(
  DEPENDENCIES
  std_msgs
  sensor_msgs
)
```
`find_package` means when build the system, they find the package named `rospy`, `std_msgs`, `sensor_msgs`.\
`generate_messages` is used when custom msg format is defined. So, by default you can use the msg module by only add the `find_package` fundction.
Also, the `generate_messages` function will be committed. In this case you are not necessary to uncommit `generate_messages`.

### 2.2. package.xml
Add below building dependancies on the package.xml code.
```
<build_depend>sensor_msgs</build_depend>
<build_export_depend>sensor_msgs</build_export_depend>
<exec_depend>sensor_msgs</exec_depend>
```
After add the block of code, the result of package.xml will be like this:
![Screenshot from 2022-07-21 18-15-25](https://user-images.githubusercontent.com/78340346/180177698-8707d8ed-7ea2-4ad5-944e-a03a323d9110.png)








