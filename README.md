# carlaEnv


```bash
docker pull carlasim/carla:0.9.15
docker run --privileged --gpus all --net=host -e DISPLAY=$DISPLAY carlasim/carla:0.9.15 /bin/bash ./CarlaUE4.sh
```

```bash
git clone -b first-step https://github.com/ruddyscent/adlab-e2e
cd adlab-e2e
sudo docker build --tag pytorch-carla:0.1 -f Dockerfile-jupyter .
sudo docker run --privileged --gpus all --net=host -e DISPLAY=$DISPLAY -it --rm  pytorch-carla:0.1 jupyter notebook
```