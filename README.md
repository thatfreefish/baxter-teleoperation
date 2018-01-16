参考内容链接：https://github.com/ptsteadman/baxter-teleoperation
## Baxter Teleoperation using Kinect and the Oculus Rift

This repository contains code for an interactive console that allows 
you to send commands to Baxter, including starting teleoperation.
Commands can be queued or interrupted for seamless operation.  Also 
supports playback of joint positions or images as specified in CSV files.

##### Setup:

First, enter the Baxter environment.
If you want to use the simulator: 

        cd ~/ros_ws
        . baxter.sh sim
        roslaunch baxter_gazebo baxter_world.launch

If you want to use the real robot:

        cd ~/ros_ws
        . baxter.sh

Second, start the kinect client in a new terminal tab:

        roslaunch openni_launch openni.launch

Third, start tracking in another termial tab:

        roslaunch openni_tracker openni_tracker.launch(原)
        rosrun openni_tracker openni_tracker（新）

Finally, enable the robot and start the console.  

        rosrun baxter_tools enable_robot.py -e
        python baxter_console.py

You can then run commands at the `>>>` prompt.  

### Commands:
- `baxter.idle()` cease teleoperation and move to an idle position (as specified by csv file) 
- `baxter.standby()` move baxter to the 'psi' kinect calibration pose
- `baxter.start_teleoperation(transition)` execute one of three transitions to teleoperation, 0=immediate, 1=with animation, 2=with image
- `baxter.queue_state(dict)` queue images or motions
- `baxter.send_image(path)` display an image on baxter's face
---------------------------------------------------------------------------------------------------
用kinect在gazebo中让baxter随动

操作的命令行：


cd ~/documents/ros

source devel/setup.bash

ifconfig

设置ip地址

gedit baxter.sh

. baxter.sh sim

roslaunch baxter_gazebo baxter_world.launch


roslaunch openni_launch openni.launch camera:=openni


cd ~/documents/ros

source devel/setup.bash

rosrun openni_tracker openni_tracker


cd ~/documents/ros

source devel/setup.bash

rosrun baxter_tools enable_robot.py -e

cd ~/桌面/baxter-teleoperation

python baxter_console.py

baxter.idle()

baxter.standby()

