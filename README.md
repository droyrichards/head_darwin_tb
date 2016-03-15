# head_darwin_tb
This repository contain ROS files for head joints of darwin-op robot

##Installation

- Install ROS
- Install Dynamixel packeges

```
sudo apt-get install ros-DISTRO-dynamixel*
```
* Install pyserial
```
sudo apt-get install python-pip
sudo pip install pyserial 
```
* Remove deprecated functions from dynamixel_io

```
#remove this
#self.ser = serial.Serial(port)
#self.ser.setTimeout(0.015)
#self.ser.baudrate = baudrate
#add this
self.ser = serial.Serial(port, baudrate, timeout=0.015)
```

## Usage
```
cd ~/catkin_ws/src
git clone https://github.com/TauraBots/head_darwin_tb.git
source ../devel/setup.bash
cd head_darwin_tb/launch
#first start de dynamixel controller
roslaunch head_darwin_tb dx_controller.launch
#start the head controller
roslaunch head_darwin_tb start_controller.launch
#run the head test
cd ../src/
python trajectory_client.py
#and go crazy
```


