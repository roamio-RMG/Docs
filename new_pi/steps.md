commands in the terminal:
sudo apt update 
sudo apt install git 

in firefox login in github with roamio account
login: roamio-RMC
passwoed: Ro424242@

ssh key for roamio-RMC github
ssh-keygen -t ed25519 -C "roamioaaqil@gmail.com"
cat ~/.ssh/id_ed25519.pub
copy paste to github

clone 

docker
    git clone git@github.com:mariame42/RMC_docker.git

roamio_brain
    git clone git@github.com:roamio-RMG/roamio_brain.git

<!-- inside the docker file there is install docker script run it 
    cd "path_to_RMC_docker"
    chmod +x install-docker.sh
    ./install-docker.sh
    <takes time , sorry this is life> -->
sudo apt update && sudo apt install -y docker.io
sudo usermod -aG docker $USER
newgrp docker


build and run docker
sudo docker build -t mariame42/ros2_jazzy_env:arm64 .
sudo docker run -it mariame42/ros2_jazzy_env:arm64
hing is connent to enable those ports for the image
<this when every t>
sudo docker run -it \
  --device=/dev/ttyUSB0 \
  --device=/dev/ttyACM0 \
  mariame42/ros2_jazzy_env:arm64


This command runs a Docker container named ros2_container from the image mariame42/ros2_jazzy_env:arm64, mounts your entire filesystem at /host inside the container, and starts an interactive Bash shell.

sudo docker run -it \
  --name ros2_container \
  -v /:/host \
  mariame42/ros2_jazzy_env:arm64 \
  /bin/bash



ssh <conection>
sudo apt update
sudo apt install openssh-server -y
sudo systemctl enable ssh
sudo systemctl start ssh
<if config command>
sudo apt install net-tools

----------cursor