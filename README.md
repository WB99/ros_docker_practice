# Building and Running Docker Image

### 1. Git Clone Repository

- git clone my repository here!

```bash
https://github.com/WB99/ros_docker_practice.git
```

### 2. Build Docker Image from Dockerfile

- `cd` into the ros package `sample_package`

```bash
cd ~/src/sample_package
```

- build docker image from dockerfile, named `ros_docker_image`

```bash
docker build -t ros_docker_image .
```

### 3. Run Docker Container

- run docker container from docker image, named `ros_docker_container`

```bash
docker run -it --name ros_docker_container ros_docker_image
```

- start new terminal in the running container

```bash
docker exec -it ros_docker_container bash
```

### 4. Running Simple Subscriber & Publisher Nodes

- run roscore in a terminal in the container

```bash
roscore
```

- in another terminal, run publisher node

```bash
docker exec -it ros_docker_container bash
rosrun sample_package talker.py
```

- in another terminal, run subscriber node

```bash
docker exec -it ros_docker_container bash
rosrun sample_package listener.py
```

### 5. Running Simple Service & Client

- run roscore in a terminal in the container

```bash
roscore
```

- in another terminal, run service

```bash
docker exec -it ros_docker_container bash
rosrun sample_package add_two_ints_server.py
```

- in another terminal, run client, providing 2 arguments for the 2 ints to be added

```bash
docker exec -it ros_docker_container bash
rosrun sample_package add_two_ints_client.py 1 4
```
