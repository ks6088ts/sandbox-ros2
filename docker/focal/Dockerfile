FROM ubuntu:20.04

# keyboard-configuration の設定画面で止まらないようにするため
# https://qiita.com/munky69rock/items/4c3a076fe496045de5f1
ARG DEBIAN_FRONTEND=noninteractive

# Installing ROS 2 via Debian Packages
# https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Install-Debians/

# Set locale
RUN apt-get update && \
    apt-get install locales && \
    locale-gen en_US en_US.UTF-8 && \
    update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8 && \
    export LANG=en_US.UTF-8

# Setup Sources
RUN apt-get install -y curl gnupg2 lsb-release && \
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | apt-key add - && \
    sh -c 'echo "deb [arch=$(dpkg --print-architecture)] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'

# Ubuntu dockerイメージをbuildするときにタイムゾーン選択で止まらないようにするため
# https://www.yamamanx.com/ubuntu-docker-build-timezone-stop/
RUN apt-get install -y tzdata

# Install ROS2 packages
RUN apt-get update && \
    apt-get install -y ros-foxy-desktop

# Sourcing the setup script
RUN echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc

# Install argcomplete
RUN apt-get install -y python3-pip && \
    pip3 install -U argcomplete

# Install utilities
RUN apt-get install -y tmux
