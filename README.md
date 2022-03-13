树莓派更改国内镜像源
sudo vim /etc/apt/sources.list


deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

sudo apt update   // 更新软件包
sudo apt upgrade  // 更新软件包
sudo apt autoremove  //卸载建议的软件
sudo apt install ubuntu-desktop //安装ubuntu桌面


ubuntu20.04 安装 ROS Noetic 详细过程
操作系统: ubuntu 20.04
ROS 版本: Noetic

sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu/ `lsb_release -cs` main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt update
sudo apt install ros-noetic-desktop-full
source /opt/ros/noetic/setup.bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc


测试 ROS 是否安装成功：
打开终端输入roscore，启动 master 节点

打开第二个终端输入rosrun turtlesim turtlesim_node

出现小乌龟后，打开第三个终端输入rosrun turtlesim turtle_teleop_key

打开新的 termial，输入以下命令rosrun rqt_graph rqt_graph，查看 ROS 节点信息

