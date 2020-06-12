.. ROS-RTSP流相机功能包：

=====================================
第九章   ROS-RTSP流相机功能包
=====================================

我们在做图像处理的时候，尤其在ROS环境下面，需要图像数据，网口的摄像头市面上比较多，技术也相对比较成熟。网络摄像头一般，
都支持RTSP的流媒体协议流。下面的操作是基于一个网口摄像头的RTSP摄像头和一台机载计算机接入图数传，机载计算机通过网口，
读取和解析RTSP的数据流成标准的ROS的image消息，有了这个消息一些ROS包里面的一些图像处理算法可以直接使用。

9.0  测试软件环境
=================

     1.ubuntu 18.04 

     2.ROS melodic

     3.RTSP流相机-ROS功能包

     rocon_rtsp_camera_relay 

     WIKI：http://wiki.ros.org/rocon_rtsp_camera_relay

     源码：https://github.com/robotics-in-concert/rocon_devices

     备注：软件版本并非强制，可自行测试。
 

9.1  创建工作空间
=================
打开新终端
::

     mkdir -p rtsp_ws/src

     cd rtsp_ws/src

     git clone https://github.com/robotics-in-concert/rocon_devices.git

     cd ..

     catkin_make

打开新终端
::
     
     gedit .bashrc

     //文档末尾添加，保存,关闭
     source ~/rtsp_ws/devel/setup.bash

     source ~/.bashrc


9.2  修改launch文件
=================

打开新终端
::

     //修改launch
     cd ~/rtsp_ws/src/rocon_devices/rocon_rtsp_camera_relay/launch/

     gedit rtsp_camera_relay.launch

添加RTSP链接，提供如下修改示例
::

     default="rtsp://192.168.1.83:554/user=admin&amp;password=&amp;channel=1&amp;stream=0.sdp?"

修改后的launch文件如下图：
     .. image:: ../images/rtsp01.png


9.3  启动ROS节点
=================
打开新终端
::

     //运行launch，启动ROS节点     
     roslaunch rocon_rtsp_camera_relay rtsp_camera_relay.launch --screen

可以再打开一个新终端，查看发布的图像话题
::

     rqt_image_view

效果如下:
     .. image:: ../images/rtsp02.png

帧率和消息如下：
     .. image:: ../images/rtsp03.jpg
20帧率左右，RTSP还是可以配置的，应该可以达到更高的帧率。还有就是在TX2下面测试，会占用额外的CPU使用率5%/10%左右。
