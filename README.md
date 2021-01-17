# deep-learn
https://www.pyimagesearch.com/2019/05/06/getting-started-with-the-nvidia-jetson-nano/


# darknet_ros

** ros melodic install

https://github.com/leggedrobotics/darknet_ros

cd catkin_workspace/src

git clone --recursive git@github.com:leggedrobotics/darknet_ros.git

cd ../

catkin_make -DCMAKE_BUILD_TYPE=Release  

or catkin build darknet_ros -DCMAKE_BUILD_TYPE=Release

rospack profile


** jetson xavier: 7.2  (https://en.wikipedia.org/wiki/CUDA#Supported_GPUs)

** add it into darknet_ros/CMakeLists.txt. 

** -gencode arch=compute_72,code=sm_72

** usb 카메라를 사용하는 ROS 프로그램 실행

sudo apt install ros-melodic-usb-cam

sudo apt-get update

roscore

rosrun usb_cam usb_cam_node

** darknet_ros.launch 파일의 image argument를 원하는 형식으로 수정

    /camera/rgb/image_raw  -> /usb_cam/image_raw

roslaunch darknet_ros darknet_ros.launch

