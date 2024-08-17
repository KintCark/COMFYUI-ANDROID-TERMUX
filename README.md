UPDATE:DON'T Install Rgthree's Extension It Uses More Ram to Speed Up your Generation. for flux Rgthree's nodes is not needed! once Rgthree's nodes gets updated to latest comfyui release I will testing it to see if I can use it in flux if not I'll let you know but right now it's working without Rgthree's nodes.





FLUX WORKS!!!!! All you need is FLUX 1 shnell gguf q4_0 from civitai then download the text encoder 2 4bit t5xxl from FLUX 4bit in huggingface then download the clip l file needed for FLUX then put the gguf in your unit folder and put clip and model.safetensors file from text encoder 2 from FLUX 4bit and put it in the clip folder in your models folder.then go to comfyui and install gguf extension then load the FLUX workflow load the unit gguf loader and replace the unet FLUX loader connect the same cables that are connected to the unet loader to the gguf unit loader. YOU NEED 12 GB RAM TO RUN FLUX Q4_0!flux qauntized models both schnell and dev q4_0,q4_1,and q5_0 Works!!


there's a special flux workflow that uses less ram by splitting the sigma I got t5xxlfp8 to work with it it makes stunning images XD!!! here is the work flow u just need to add the gguf extension like I said above: https://drive.google.com/file/d/14TPL36iHXB2B6R12VZfemKaWfNhRHu3o/view?pli=1

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


SDXL/SD3/FLUX

cd ComfyUI && python main.py --cpu --disable-xformers --preview-method taesd --cpu-vae --disable-cuda-malloc --use-split-cross-attention --force-fp16 --fp8_e4m3fn-text-enc --fp8_e4m3fn-unet --disable-smart-memory

SD1.5 ANIMATEDIFF 

cd ComfyUI && python main.py --cpu --preview-method taesd --cpu-vae --disable-cuda-malloc --use-split-cross-attention --disable-metadata --force-fp16 --fp16-unet --fp16-text-enc

Install ComfyUI Manager

cd ComfyUI

cd custom_nodes

git clone https://github.com/ltdrdata/ComfyUI-Manager.git


After You install Manager Make Sure To Install Efficiency Nodes!! they are better for Performance And are less messy!!!


PixArt Sigma XL 2 Works on 12gb Ram!!!

go here to see how to install it and the required files.

https://civitai.com/models/420163/abominable-spaghetti-workflow-pixart-sigma

SD3 clip included Model Works its only 5gb and makes stunning portraits in 6-7 steps. it took an hour to make 7 steps but that's fine with me. 12gb ram is required but if u have a phone with more ram ull be able to use sd3 with t5xxl included. 😉 

u can make 512x512 and 256x256 images they are alot faster especially 256x256

the t5xxl sd3 included version doesn't work on 12gb Ram cause actually termux says I have 10602 mb of ram not 12 but on my system it says I got 12gb so termux is not seeing all my ram or I got scamed when buying my phone idk but for now I only can use the 5gb model


I Found an. Animatediff Workflow That's Twice as Fast!!! it's better than Gen 2 nodes😁 gen1 animatediff nodes are faster and use less memory
here is the link just copy the code go to a text editor and paste all the json code into it then save it as json file. i can generate 8 batch 2-4 steps in 10 to 7 minutes!!!

https://github.com/dezi-ai/ComfyUI-AnimateLCM/blob/main/workflows/animatelcm.json

Make Sure you use taesd and only 320x512 I tried 512x512 but it crashed we finally can use text to video offline on portable devices don't have to wait hours for generated video plus it's lcm😄

Ollama LLM Works But only light weight models 0.5-3b models as bigger models use more ram. u can run multiple sessions in termux to use it first install ollama in termux after installing  ubuntu

curl -fsSL https://ollama.com/install.sh | sh

then type ollama serve then start a new termux session,login to ubuntu.

then go to Olla website and pick any 0.5-3b model copy the name of the model

then make sure u know the correct model weight
then in the new termux session type

ollama pull dolphin-phi:2.7b

then after download finished start comfyui
then download an if_ai node workflow then download all requirements.then download marco file manager in Google play store then Move the IF_AI folder from the ComfyUI-IF_AI_tools to inside the root input ComfyUI/input/ then after that you may have trouble seeing your ollama models, don't worry they are there just tap local host and put 127.0.0.1 then restart comfyui server,after that tap on a different model then u should see some models appear go back to ollama and models should be there.



