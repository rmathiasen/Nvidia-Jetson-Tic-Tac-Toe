# Nvidia-Jetson-Tic-Tac-Toe

This is a project that runs on the Nvidia Jetson Nano within the Nvidia DLI Jupyter Lab Docker container. This project uses a classification model that you train yourself to detect moves on a physical tic-tac-toe board using a webcam. You are able to play against the computer using a physical tic-tac-toe board and your custom-trained classification model.

 <br>
Watch the tutorial and demo on YouTube here: 

 <br>  <br>
Setup Instructions:

1. Download the Nvidia Jetson OS Image from https://developer.nvidia.com/embedded/jetpack-sdk-461
2. Create a bootable SD card, setup Ubuntu, and update your system by running:  sudo apt-get update && sudo apt-get upgrade
3. Install OpenCV by running:  pip install opencv-python
4. Setup the Nvidia Jetson DLI Docker container by running:  echo "sudo docker run --runtime nvidia -it --network host
    --volume ~/nvdli-data:/nvdli-nano/data
    --volume /tmp/argus_socket:/tmp/argus_socket
    --device /dev/video0
    nvcr.io/nvidia/dli/dli-nano-ai:v2.0.2-r32.7.1" > docker_dli_run.sh
5. Make the script executable by running:  chmod +x docker_dli_run.sh
6. Run the script to create the Docker container. This will create a new Docker container with its own files seperate from other containers each time you run it:  ./docker_dli_run.sh
7. In a new terminal window, get the name of the docker container you just created by running:  sudo docker container ls -a
8. When you want to start the container to access Jupyter Lab, run:  sudo docker start docker_name_here
9. Once the Docker container is running, access Jupyter Lab by clicking on the link in your terminal. You can now import the Play Game.ipynb file from this repo by dragging it into the file browser built into Jupyter Lab.
10. I included a PDF for a tic-tac-toe board to have more consistency for model training and testing. You can print these out if you'd like to use them and eliminate a source of inconsistency in your model training.
