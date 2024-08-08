Animatediff Works only on 12gb Ram and Up.
Animatediff lcm is best cause it's required less steps,make sure u pick the animate lcm lora and animate lcm checpoint!,or you will have burnt images
I figured this after struggling with 3 videos 😁😂
useing an lcm model is even better for higher quality videos.




Install ComfyUI on Termux (Android) + PRoot This will guide you on installing ComfyUi on Termux (Android) + PRoot Distro. Make sure that you have a high-end phone but it can work on lower end devices with 8gb ram it will depend on the cpu ethier snapdragon or mali

Prerequisites First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot


pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

Installing ComfyUI Run below commands sequentially as root user in Ubuntu
Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-distutils python3-pip python3-venv python-is-python3 -y && pip install ffmpeg && apt dist-upgrade -y && apt install wget && apt-get install libgl1 libglib2.0-0 libsm6 libxrender1 libxext6 -y && apt-get install google-perftools &&
apt install libgoogle-perftools-dev && pip install moviepy==1.0.3


Clone the repository

git clone https://github.com/comfyanonymous/ComfyUI

Change the current directory

cd ComfyUI

export ANDROID_DATA=anything

Install required Python packages

pip install -r requirements.txt


Navigate to the webui in your browser

http://127.0.0.1:8188

To start after rebooting termux after first installation

cd ubuntu-in-termux && ./startubuntu.sh


I just Discovered The Best Args Combination you can use SDXL AND LORAS!!! It's 16 seconds per Step!! 50 seconds for 512x320!!! XD it's BLAZING FAST!!!

if u wanna use animatediff u have to change the text-enc and unet to fp16 fp8 works best for sdxl.


SDXL/SD3

cd ComfyUI && python main.py  --cpu --disable-xformers --preview-method taesd --cpu-vae --disable-cuda-malloc --use-split-cross-attention --disable-metadata --force-fp16 --fp8_e4m3fn-text-enc --fp8_e4m3fn-unet --dont-upcast-attention

SD1.5 ANIMATEDIFF 

cd ComfyUI && python main.py --cpu --preview-method taesd --cpu-vae --disable-cuda-malloc --use-split-cross-attention --disable-metadata --force-fp16 --fp16-unet --fp16-text-enc

Install ComfyUI Manager

cd ComfyUI

cd custom_nodes

git clone https://github.com/ltdrdata/ComfyUI-Manager.git


After You install Manager Make Sure To Install Efficiency Nodes!! they are better for Performance And are less messy!!! Also install Rgthree's nodes they have an optimized feature that helps load sdxl models.


PixArt Sigma Works on 12gb Ram!!!

go here to see how to install it and the required files.

https://civitai.com/models/420163/abominable-spaghetti-workflow-pixart-sigma


SD3 clip included Model Works its only 5gb and makes stunning portraits in 6-7 steps. it took an hour to make 7 steps but that's fine with me. don't use the sd3 t5xxl version as it's 10gb and won't work cause the sd3 base model is too big. t5xxl only works with sd1.5 cause it's only 2gb size.12gb ram is required but if u have s phone with more ram ull be able to use sd3 with t5xxl included. 😉 

u can make 512x512 and 256x256 images they are alot faster especially 256x256