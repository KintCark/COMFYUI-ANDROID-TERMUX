Install ComfyUI on Termux (Android) + PRoot This will guide you on installing ComfyUi on Termux (Android) + PRoot Distro. Make sure that you have a high-end phone to actually make this usable. On my phone with 12GB RAM, launch the webui alone take at least ~ 2 GB RAM, thus making it impossible to load any model and process further.

Prerequisites First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

Installing ComfyUI Run below commands sequentially as root user in Ubuntu
Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y

Install required extensions

apt-get install libgl1 libglib2.0-0 libsm6 libxrender1 libxext6 -y

Clone the repository

git clone https://github.com/comfyanonymous/ComfyUI

Change the current directory

cd ComfyUI

'Fix' the issue with Python running in PRoot Newer Phones Android 13-14 don't need this Command but all phones are Different.

export ANDROID_DATA=anything

Install required Python packages

pip install -r requirements.txt

pip install ffmpeg

Navigate to the webui in your browser

http://127.0.0.1:8188

To start after rebooting termux after first installation

cd ubuntu-in-termux && ./startubuntu.sh

cd ComfyUI && python main.py --cpu --force-fp16 --force-upcast-attention --fp16-vae --disable-smart-memory --use-split-cross-attention --preview-method taesd --fp16-text-enc --fp16-unet --cpu-vae


Install ComfyUI Manager

cd ComfyUI

cd custom_nodes

git clone https://github.com/ltdrdata/ComfyUI-Manager.git