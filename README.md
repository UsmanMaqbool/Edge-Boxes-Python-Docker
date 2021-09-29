# Edge-Boxes-Python-Docker
Docker image and Test Example of Edge Boxes: Locating Object Proposals from Edges

Credits: https://stackoverflow.com/questions/54843550/edge-box-detection-using-opencv-python

<p align="center">
  ⭐️ If you like MAQBOOL, give it a star on GitHub! ⭐️
  <br>
  <a href="https://twitter.com/MUsmanMBhutta"><img src="https://img.shields.io/twitter/follow/MUsmanMBhutta.svg?style=social" alt="Twitter Follow" /></a>
  <a href="#license"><img src="https://img.shields.io/github/license/sourcerer-io/hall-of-fame.svg?colorB=ff0000"></a>
</p>

## Clone

```
git clone https://github.com/UsmanMaqbool/Edge-Boxes-Python-Docker.git

```
## Run Docker Container
```sh
docker build -t opencv3-py3-gpu - < Dockerfile-py3-cuda

xhost +local:root

sudo docker run --gpus all -it \
    --volume="/tmp/.X11-unix:/tmp/.X11-unix" \
    --env="DISPLAY=$DISPLAY" \
    --env="QT_X11_NO_MITSHM=1" \
    --env="XAUTHORITY=$XAUTH" \
    --volume="$XAUTH:$XAUTH" \
    --runtime=nvidia \
    --publish=8001:8888 \
    --publish=6001:6006 \
    \
    #--workdir="/container_ws/" \
    #--volume="/home/leo/usman_ws/:/container_ws/" \
    #--name="maqbool" \
    opencv3-py3-gpu /bin/bash
```

## Run Example
python3 edgeboxes_demo.py models/model.yml.gz test.jpg