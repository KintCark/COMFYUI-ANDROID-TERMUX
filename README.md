Before installing virtual environment
make sure u install ubuntu in termux first 


Looks like Python 3.12 actually Works!! U have to create a virtual environment so here is the guide:


To run ComfyUI in a separate environment on Termux with Python 3.10.11, follow these steps:


---

1. Install Required Packages

First, ensure your Termux is updated and install necessary packages:

apt update -y && apt upgrade -y
apt install python3-full git ffmpeg


---

2. Install & Setup a Virtual Environment

Create and activate a virtual environment:

python3 -m venv comfyui-env
source comfyui-env/bin/activate


---

3. Clone ComfyUI Repository

Download ComfyUI from GitHub:

git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI


---

4. Install Dependencies

Since you are using CPU-only, install the necessary requirements:

pip install --no-cache-dir torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
pip install --no-cache-dir -r requirements.txt


---

5. Run ComfyUI

Now, launch ComfyUI in your virtual environment:

python main.py


---

6. (Optional) Deactivate Environment

If you want to exit the virtual environment, run:

deactivate


---

Additional Notes:

This setup ensures ComfyUI runs in a separate environment, avoiding conflicts with system packages.

If your Termux does not have python-full=3.10.11 available, consider using a Proot-Distro like Ubuntu to run Python 3.10.11.

If running into RAM issues, consider adding swap memory in Termux.

Prerequisites First you have to install Termux and install PRoot. Then install and login to Ubuntu in PRoot

pkg updated && pkg upgrade -y && termux-setup-storage && pkg install wget -y && pkg install git -y && pkg install proot -y && cd ~ && git clone https://github.com/MFDGaming/ubuntu-in-termux.git && cd ubuntu-in-termux && chmod +x ubuntu.sh && ./ubuntu.sh -y && ./startubuntu.sh

Installing ComfyUI Run below commands sequentially as root user in Ubuntu Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3 -y && pip install ffmpeg && apt dist-upgrade -y && apt install wget && apt-get install libgl1 libglib2.0 libsm6 libxrender1 libxext6 -y && apt-get install google-perftools && apt install libgoogle-perftools-dev && pip install moviepy==1.0.3 && pip install accelerate && pip install setuptools && pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu && pip install sageattention && apt-get install git-lfs && pip install diffusers && pip install gguf

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

SDXL/SD3/SD3.5/FLUX/SD1.5/AnimateDiff-Evolved

cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --force-fp16 --fp8_e4m3fn-unet --disable-xformers --fp8_e4m3fn-text-enc --fast --disable-smart-memory --use-split-cross-attention

Animatediff FP16-Better Quality

cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --use-pytorch-cross-attention --force-fp16 --fp16-unet --disable-xformers --fp16-text-enc --fast --disable-smart-memory

Sana 600M

cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --use-pytorch-cross-attention --force-fp16 --bf16-unet --disable-xformers --fp16-text-enc --fast --disable-smart-memory --fast

Pixart Sigma Portable

cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --use-pytorch-cross-attention --force-fp16 --fp8_e4m3fn-unet --disable-xformers --fp8_e4m3fn-text-enc --disable-smart-memory --fast

Animatediff img2vid


cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --use-pytorch-cross-attention --force-fp32 --disable-xformers --fp16-text-enc --fast --disable-smart-memory --fp16-vae --fp16-unet


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

I Found an. Animatediff Workflow That's Twice as Fast!!! it's better than Gen 2 nodes😁 gen1 animatediff nodes are faster and use less memory here is the link just copy the code go to a text editor and paste all the json code into it then save it as json file. i can generate 8 batch 2-4 steps in 10 to 7 minutes!!!

https://github.com/dezi-ai/ComfyUI-AnimateLCM/blob/main/workflows/animatelcm.json

Make Sure you use taesd and only 320x512 I tried 512x512 but it crashed we finally can use text to video offline on portable devices don't have to wait hours for generated video plus it's lcm😄

Ollama LLM Works But only light weight models 0.5-3b models as bigger models use more ram. u can run multiple sessions in termux to use it first install ollama in termux after installing ubuntu

curl -fsSL https://ollama.com/install.sh | sh

then type ollama serve then start a new termux session,login to ubuntu.

then go to Olla website and pick any 0.5-3b model copy the name of the model

then make sure u know the correct model weight then in the new termux session type

ollama pull dolphin-phi:2.7b

then after download finished start comfyui then download an if_ai node workflow then download all requirements.then download marco file manager in Google play store then Move the IF_AI folder from the ComfyUI-IF_AI_tools to inside the root input ComfyUI/input/ then after that you may have trouble seeing your ollama models, don't worry they are there just tap local host and put 127.0.0.1 then restart comfyui server,after that tap on a different model then u should see some models appear go back to ollama and models should be there.

FLUX WORKS!!!!! all gguf versions work!! we can make stunning images with shnell q8 t5xxlfp16 and only 1 step XD!! use q8_0 flux version and t5xxlfp16 for best quality u only need this workflow:https://civitai.com/models/652884/flux-gguf-android-termux download v2.0

Update102924:sd3.5 large,large turbo, and medium,all works use sd3.5 large gguf and if u have more ram use sd3.5 medium with gguf t5xxl q5_0 XD it's faster than flux!!

update011925 I finally figured out how to fix bad colored low quality animations with Animatediff all u gota do is put all motion model samplers at lcm then on ksampler put sampler on lcm and scheduler on ddim_uniform
use motion model v3 fp16 it is faster than Animatediff Lightning 😀 just use lcm lora for non lcm models.also put context stride at 3 and overlap at 8 leave length at 16