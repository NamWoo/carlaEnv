
# 사전 준비사항

`carla-unreal`, `carla-ros`, `carla-jupyter`


## additional carla docker
```bash
docker run -it --rm   --ipc=host   --privileged   --ulimit memlock=-1   --ulimit stack=67108864   -v "$(pwd)/home:/workspace"   -v /tmp/.X11-unix:/tmp/.X11-unix   -v /dev/dri:/dev/dri   -v "${HOME}:${HOME}"   -v "${XAUTHORITY:-$HOME/.Xauthority}:/root/.Xauthority"   -v /etc/group:/etc/group:ro   -v /etc/passwd:/etc/passwd:ro   -v /etc/shadow:/etc/shadow:ro   -v /etc/sudoers.d:/etc/sudoers.d:ro   --user "${UID}"   --env DISPLAY=${DISPLAY}   --env QT_X11_NO_MITSHM=1   --env QT_QPA_PLATFORM=xcb   --env SDL_VIDEODRIVER=x11   --env NVIDIA_DRIVER_CAPABILITIES=all   --network host   --gpus all   --workdir /workspace   --name carla_container   adlab-e2e-carla:latest   bash /home/carla/CarlaUE4.sh -carla-rpc-port=${CARLA_RPC_PORT:-2000} -carla-streaming-port=${CARLA_RPC_PORT:-2001}
```



## carla ros run code

### teminal-1

```bash
docker exec -it adlab-e2e-ros-1 bash

#docker env
ros2 launch carla_ros_bridge carla_ros_bridge.launch.py
```

### teminal-2

```bash
docker exec -it adlab-e2e-ros-1 bash

#docker env
ros2 launch carla_spawn_objects carla_spawn_objects.launch.py
```

### teminal-3

```bash
docker exec -it adlab-e2e-ros-1 bash

#docker env
pip install pygame
ros2 launch carla_manual_control carla_manual_control.launch.py
```

### teminal-4

```bash
docker exec -it adlab-e2e-ros-1 bash

#docker env
rviz2
```

### teminal-5

```bash
docker exec -it adlab-e2e-ros-1 bash

#docker env
ros2 topic list
```




