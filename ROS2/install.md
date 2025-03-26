1. 配置ubuntu的软件和更新
  a. ubuntu的软件和更新 => Ununtu软件 => 可从互联网下载 => 四个选项勾选
2. 设置安装源
  sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu/ `lsb_release -cs` main" > /etc/apt/sources.list.d/ros-latest.list'
3. 设置key
  sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
4. 安装
  a. 更新apt  sudo apt update
  b. 安装ROS sudo apt install ros-noetic-desktop-full
5. 配置环境变量
	echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
	source ~/.bashrc

注：
1. 卸载
	sudo apt-get remove ros-noetic-*
2. ROS官网
	http://wiki.ros.org/noetic/Installation/Ubuntu

