## LAB5: Robot Operation System

### 任务：
>1. 安装ros
>2. 记录过程
>3. 记录个人感想和体会

### 安装ros过程记录
>#### 添加软件源到sources.list
>sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
>![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/30635510.jpg)
>#### 设置密钥
>sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
>#### 安装
>##
>#####1.确认Debian的软件包索引是最新的
>sudo apt-get update
>#####2.完全安装ROS Desktop
>sudo apt-get install ros-jade-desktop-full
>![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-7/80832235.jpg)
>#####3.获取包
>apt-cache search ros-jade
>
>##
>#### 初始化rosdep
>sudo rosdep init
>
>rosdep update
>#### 设置环境，添加环境变量
>echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
>
> source ~/.bashrc 

### 实验感想
>以下为百度：
>
>ROS（机器人操作系统，RobotOperatingSystem），是专为机器人软件开发所设计出来的一套电脑操作系统架构。它是一个开源的元级操作系统（后操作系统），提供类似于操作系统的服务，包括硬件抽象描述、底层驱动程序管理、共用功能的执行、程序间消息传递、程序发行包管理，它也提供一些工具和库用于获取、建立、编写和执行多机融合的程序。
>
>虽然安装ros过程中遇到的障碍相对cartographer还好，虽然现在对ros也还没有什么特别大的概念，不过learning by doing，还是一步步在对这些慢慢熟悉和了解，都是一步步的过程，慢慢在做中摸索。



