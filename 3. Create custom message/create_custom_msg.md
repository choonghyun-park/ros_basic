# Create custom message
You can create your own message format by build the catkin_ws.\
For example, if you want to use the below message type, you just follow this tutorial. [Reference](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv)\
Message format :
```
string first_name
string last_name
uint8 age
uint32 score
```
## 1. Create msg directory and create message
You have to make a msg file which has the message description.\
Terminal :
```
roscd beginner_tutorials
mkdir msg
cd msg
touch Num.msg
```
In your Num.msg file, add the variable type and name :
```
[variable_type] [variable name]
```
So, the content of Num.msg will be :
```
string first_name
string last_name
uint8 age
uint32 score
```

## 2. package.xml
add `message_generation`, `message_runtime` in dependancy part.
```
  <build_depend>message_generation</build_depend>
  <exec_depend>message_runtime</exec_depend>
```

## 3. CMakeLists.txt
In the `find_package` function, add the `message_generation`
```
find_package(catkin REQUIRED COMPONENTS
   roscpp
   rospy
   std_msgs
   message_generation
)
```
In the `catkin_package` function, add the `message_runtime` like below. If the `catkin_package` codes are committed, please uncommit the code block.

```
catkin_package(
  ...
  CATKIN_DEPENDS message_runtime ...
  ...)
```
Also uncommit the add_message_files function and add Num.msg 
```
add_message_files(
  FILES
  Num.msg
)
```
Also uncommit the `generate_messages` function. 
```
generate_messages(
  DEPENDENCIES
  std_msgs
)
```
## 4. Build your catkin_ws
As you reviced the `CMakeLists.txt` and `package.xml`, you have to build your workspace again.
```
cd ~/simpleros_ws
catkin_make
```

## 4. your source code
Now in your source code, you have to add the import statement.\
In your source code :
```python
from beginner_tutorials.msg import Num  
```
Usage :
```python
from [package_name.msg] import [message_file]
```


