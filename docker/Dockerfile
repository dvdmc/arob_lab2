FROM osrf/ros:noetic-desktop-full

# Install dependencies
RUN apt-get update && apt-get install -y git tmux vim xterm curl ssh tree python3-catkin-tools python3-tk nano

RUN echo "set -g mouse on" > /root/.tmux.conf

# Create catkin workspace
RUN mkdir -p /root/catkin_ws/src/

# Clone lab repositories
RUN git clone https://github.com/ros-geographic-info/unique_identifier.git /root/catkin_ws/src/unique_identifier && \
    git clone https://github.com/ros-geographic-info/geographic_info.git /root/catkin_ws/src/geographic_info && \
    git clone https://github.com/RAFALAMAO/hector_quadrotor_noetic.git /root/catkin_ws/src/hector_quadrotor_noetic

# Build catkin workspace to check that everything works
RUN /bin/bash -c '. /opt/ros/noetic/setup.bash && cd /root/catkin_ws && catkin build'
