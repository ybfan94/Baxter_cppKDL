# Baxter cppKDL
A Kinematic Solver for Baxter Robot that written in C++.

# Introduction
Baxter cppKDL is a C++ library that offers forward kinematics and inverse kinematic calculation. We got inspired by [Baxter_pyKDL](http://sdk.rethinkrobotics.com/wiki/Baxter_PyKDL) and tried to build a similiar library for C++ users. It aimed to reduce the difficuty of using orocos KDL for the kinematic and dynamic analysis of Baxter in C++.

# Prerequisite
This library uses functions in orocos KDL(Kinematics and Dynamics Library). Thus, this package has to be installed. Please refer to [http://www.orocos.org/kdl/installation-manual] for more information.

# Build the baxter_cppkdl package
```
 $ cd ~/ros_ws/src
 $ git clone https://github.com/xwying/Baxter_cppKDL.git
 $ cd ~/ros_ws
 $ source ./baxter.sh
 $ catkin_make
```

# Class
+ baxter_kinematics

    Arguments:limb(required), it could be 'left' or 'right'.
    
    Description: Initialize the class with specific limb.
# Method
+ forward_kinematics

    Arguments:result(array)(required), joint_value(array)(optional)
    
    Description: Solves the forward kinematics, if the joint value is unspecified, it will read the current joint angle from Baxter. The result will write to result_array.
    
+ inverse_kinematics

    Arguments:
    
        result(array)(required)
        position(array)(required) - Cartesian Position, Orientation (optional) [x, y, z]
        orientation(array)(optional) - Quaternion Orientation [i, j, k, w]
        seed(array)(optional) - Seeded joint angles for solver. Searchs out from seeded joint angles for IK solution [s0, s1, e0, e1, w0, w1, w2]
     
    Description: Solves the inverse kinematics using, providing joint angles given a Cartesian pose
    

This is also our first ROS project. If you have any problem please feel free to contact sslf[at]foxmail[dot]com or ybfan910[at]163[dot]com
