# Create package tutorial

## 1. How to create package
In the `catkin_ws/src` directory :
```
catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
```
**Note** : Usage : 
```
catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
```
Then `src`, `package.xml` and `CMakeLists.txt` will be created
## 2. Build the workspace
```
cd ~/simpleros_ws
catkin_make
```
## 3. Description of catkin package
### 3.1. src
Your all source code should be located in src directory. The source code can be python or cpp resources.
### 3.2. package.xml
The `package.xml` file contains the dependancy informations. While build the catkin_ws, the depandancy module made by referencing the this file. If you want use any other module(rospy, roscpp, std_msgs, nav_msgs), You should add the dependency of these module in this file.
### 3.3. CMakeLists.txt
The CMakeLists.txt have the information of used source code or message, package. The information usually indicates the location of these files and CMakeLists.txt also used in build steps. 





