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


6. 安装相关依赖
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

sudo rosdep init


ERROR: cannot download default sources list from:
https://raw.githubusercontent.com/ros/rosdistro/master/rosdep/sources.list.d/20-default.list
Website may be down.
<urlopen error <urlopen error _ssl.c:1128: The handshake operation timed out> (https://raw.githubusercontent.com/ros/rosdistro/master/rosdep/sources.list.d/20-default.list)>

解决报错的方法：
cd /usr/lib/python3/dist-packages/

find . -type f | xargs grep "raw.githubusercontent"

sudo vim ./rosdistro/__init__.py
DEFAULT_INDEX_URL = 'https://raw.githubusercontent.com/ros/rosdistro/master/index-v4.yaml'  => DEFAULT_INDEX_URL = 'https://gitee.com/zhao-xuzuo/rosdistro/raw/master/index-v4.yaml'

sudo vim ./rosdep2/gbpdistro_support.py
同上替换 找raw.githubusercontent.com

sudo vim rosdep2/sources_list.py
同上替换 找raw.githubusercontent.com

sudo vim ./rosdep2/rep3.py
同上替换 找raw.githubusercontent.com

成功执行
sudo rosdep init
rosdep update
