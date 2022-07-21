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
If you need dependancy of std_msgs :
```
catkin_create_pkg beginner_tutorials std_msgs
```

