FROM ros:noetic

RUN apt-get update && \
    apt-get install -y --no-install-recommends g++ \
    make \
    python3-pip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists

WORKDIR /home/ros_docker_ws/

COPY . src/docker_sample_package/

RUN /ros_entrypoint.sh catkin_make && sed -i '$isource "/home/ros_docker_ws/devel/setup.bash"' /ros_entrypoint.sh