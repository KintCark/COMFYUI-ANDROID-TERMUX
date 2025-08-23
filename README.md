Install Decord

1st

git clone --recursive https://github.com/dmlc/decord

2nd

apt-get install libavformat-dev libavfilter-dev libavdevice-dev ffmpeg

third>PRESS ENTER ON make!

cd decord mkdir build && cd build cmake .. -DUSE_CUDA=0 -DCMAKE_BUILD_TYPE=Release make

Forth

cd ../python python3 setup.py install --user









I Found an arg --cache-none that reduces ram usage I didn't know this existed I'm testing it now I'll be back with results👍



enjoy ltxv!! on Android Termux!!!😉

Wan 2.1, wan 2.2, hunyuan, ltxv Works but only maxed to 256x256 and 512x512 12gb Ram use gguf version!


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

pkg update -y && pkg install wget curl proot tar -y && wget https://raw.githubusercontent.com/AndronixApp/AndronixOrigin/master/Installer/Ubuntu22/ubuntu22.sh -O ubuntu22.sh && chmod +x ubuntu22.sh && bash ubuntu22.sh 


Installing ComfyUI Run below commands sequentially as root user in Ubuntu Install basic tools

apt update && apt upgrade -y && apt-get install curl git gcc make build-essential python3 python3-dev python3-pip python3-venv python-is-python3 -y && pip install ffmpeg && apt dist-upgrade -y && apt install wget && apt-get install libgl1 libglib2.0 libsm6 libxrender1 libxext6 -y && apt-get install google-perftools && apt install libgoogle-perftools-dev && pip install moviepy==1.0.3 && pip install accelerate && pip install setuptools && pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu && pip install sageattention && apt-get install git-lfs && pip install diffusers && pip install gguf && pip install numba && pip install pynvml && pip install wheel && pip install docutils && pip install use && pip install numpy._utils && pip install fonttools>=4.22.0 && pip install simpleeval && pip install numexpr && pip && pip install insightface && pip install open-clip-torch && pip install einops && pip install cython && pip install polygraphy && pip install torchsde && pip install wget 


after finish installing logout of Ubuntu by typing logout then press enter then run this command: pkg install python then check which version of python u have with this: python --version
Clone the repository

git clone https://github.com/comfyanonymous/ComfyUI


I Found a modded comfyui that only uses cpu this is perfect for android hopefully it's faster!


git clone https://github.com/ArdeniusAI/ComfyUI-cpu.git


Change the current directory

cd ComfyUI

if u wanna try ComfyUI-cpu then 

cd ComfyUI-cpu

export ANDROID_DATA=anything

Install required Python packages

pip install -r requirements.txt

Navigate to the webui in your browser

http://127.0.0.1:8188

To start after rebooting termux after first installation

./start-ubuntu22.sh

cd ComfyUI && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --fp8_e4m3fn-unet --fp8_e4m3fn-text-enc --fast --disable-smart-memory --supports-fp8-compute --async-offload --use-pytorch-cross-attention --force-fp16 --cache-none




COMFYUI-CPU

cd ComfyUI-cpu && python main.py --cpu --disable-xformers --cpu-vae --disable-cuda-malloc --fp8_e4m3fn-unet --fp8_e4m3fn-text-enc --fast --disable-smart-memory --use-pytorch-cross-attention --force-fp16  --fp16-vae

Install ComfyUI Manager

cd ComfyUI

cd custom_nodes

git clone https://github.com/ltdrdata/ComfyUI-Manager.git

After You install Manager Make Sure To Install Efficiency Nodes!! they are better for Performance And are less messy!!!


Comfyui Cli Install

pip install comfy-cli

comfy --install-completion


Install Ollama

Update Ubuntu: apt update && apt upgrade -y

Install deps: apt install git wget curl jq

Install Ollama: curl -fsSL https://ollama.com/install.sh | sh

Start Ollama: ollama serve &

Run a model that will work for your device like Qwen2:0.5b: ollama run qwen2:0.5b --verbose





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


To install `matplotlib.pyplot` in Termux on Android (Ubuntu Linux environment isn't necessary), follow these steps:

### 1. **Update Termux Packages**
   ```bash
   pkg update
   pkg upgrade
   ```

### 2. **Install Required Dependencies**
   ```bash
   pkg install python python-numpy libjpeg-turbo libpng
   ```

### 3. **Install Matplotlib via pip**
   ```bash
   pip install matplotlib --no-build-isolation
   ```
   The `--no-build-isolation` flag avoids build issues in Termux's environment.

---

### **Troubleshooting Common Issues**
#### If installation fails:
1. **Ensure all dependencies are installed**:
   ```bash
   pkg install freetype pkg-config libcrypt
   ```

2. **Install build tools** (if needed for dependencies):
   ```bash
   pkg install clang make binutils
   ```

3. **Reinstall with verbose mode** (if errors persist):
   ```bash
   pip install -v matplotlib --no-build-isolation
   ```

---

### **Test the Installation**
1. Launch Python:
   ```bash
   python
   ```
2. In the Python shell:
   ```python
   import matplotlib.pyplot as plt
   plt.plot([1, 2, 3], [4, 5, 1])
   plt.show()
   ```
   - If no GUI appears (common in Termux), save the plot instead:
     ```python
     plt.savefig("test.png")
     ```
     View the image with a file manager or Termux command (e.g., `termux-open test.png`).

---

### **Notes**
- **GUI Support**: Termux lacks native GUI, so `plt.show()` won't display plots interactively. Save plots as files instead.
- **Lightweight Alternative**: Use `termplotlib` for text-based plots in the terminal:
  ```bash
  pip install termplotlib
  ```

This method ensures a smooth installation of `matplotlib` in Termux without requiring an Ubuntu environment.






[-h] [--listen [IP]] [--port PORT]                    [--tls-keyfile TLS_KEYFILE]                           [--tls-certfile TLS_CERTFILE]
               [--enable-cors-header [ORIGIN]]
               [--max-upload-size MAX_UPLOAD_SIZE]
               [--base-directory BASE_DIRECTORY]
               [--extra-model-paths-config PATH [PATH ...]]
               [--output-directory OUTPUT_DIRECTORY]
               [--temp-directory TEMP_DIRECTORY]
               [--input-directory INPUT_DIRECTORY]
               [--auto-launch]
               [--disable-auto-launch]
               [--cuda-device DEVICE_ID]
               [--cuda-malloc | --disable-cuda-malloc]
               [--force-fp32 | --force-fp16]
               [--fp32-unet | --fp64-unet | --bf16-unet | --fp16-unet | --fp8_e4m3fn-unet | --fp8_e5m2-unet | --fp8_e8m0fnu-unet]
               [--fp16-vae | --fp32-vae | --bf16-vae]
               [--cpu-vae]
               [--fp8_e4m3fn-text-enc | --fp8_e5m2-text-enc | --fp16-text-enc | --fp32-text-enc | --bf16-text-enc]
               [--force-channels-last]
               [--directml [DIRECTML_DEVICE]]
               [--oneapi-device-selector SELECTOR_STRING]
               [--disable-ipex-optimize]
               [--supports-fp8-compute]
               [--preview-method [none,auto,latent2rgb,taesd]]
               [--preview-size PREVIEW_SIZE]
               [--cache-classic | --cache-lru CACHE_LRU | --cache-none]
               [--use-split-cross-attention | --use-quad-cross-attention | --use-pytorch-cross-attention | --use-sage-attention | --use-flash-attention]
               [--disable-xformers]
               [--force-upcast-attention | --dont-upcast-attention]
               [--gpu-only | --highvram | --normalvram | --lowvram | --novram | --cpu]
               [--reserve-vram RESERVE_VRAM]
               [--async-offload]
               [--default-hashing-function {md5,sha1,sha256,sha512}]
               [--disable-smart-memory]
               [--deterministic] [--fast [FAST ...]]
               [--mmap-torch-files]
               [--dont-print-server]
               [--quick-test-for-ci]
               [--windows-standalone-build]
               [--disable-metadata]
               [--disable-all-custom-nodes]
               [--whitelist-custom-nodes WHITELIST_CUSTOM_NODES [WHITELIST_CUSTOM_NODES ...]]
               [--disable-api-nodes] [--multi-user]
               [--verbose [{DEBUG,INFO,WARNING,ERROR,CRITICAL}]]
               [--log-stdout]
               [--front-end-version FRONT_END_VERSION]
               [--front-end-root FRONT_END_ROOT]
               [--user-directory USER_DIRECTORY]
               [--enable-compress-response-body]
               [--comfy-api-base COMFY_API_BASE]
               [--database-url DATABASE_URL]





UPGRADE PYTHON TO 3.13 AS THE UBUNTU DEFAULT TO 3.10 ULL BE ABLE TO USE NEW NODES LIKE LTXV

apt install wget build-essential libreadline-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev


2. Then, select download the most recent dev version of Python 3.13 (so far Python-3.13.0.tar.xz) from the link page below:


https://www.python.org/ftp/python/3.13.0/

Download Python 3.13


3. Next, extract the source tarball in file manager. Then, right-click on extracted folder and select “Open in terminal” to open that folder as working directory in terminal.




4. In the pop-up terminal, configure the source via command:

./configure --enable-optimizations
For choice, you can run ./configure --help to print more configure options.

Then, compile by starting 4 threads in parallel:

make -j4
And finally install Python 3.13:

make install
Finally, verify via command: python3.13 --version and pip3.13 --version.

Uninstall:
For Python 3.13 installed from PPA, open terminal and run command to remove it:

apt remove --autoremove python3.13
Also remove the PPA by running command:

sudo add-apt-repository --remove ppa:deadsnakes/ppa
If you compiled it from source, then try running the command below from source folder until you removed it:

sudo make uninstall
Or, manually delete all the corresponding files and folders (run whereis python3.13 to tell).


LTXV is Amazing its perfect for cpu users itz fast and uses less ram 9.6 with 9.8 13b vae is very fast like so ic speed u can do higher resolution with ltxv also on Android

if u get an error saying no support sdpa when trying llm just do this:


pip install transformers==4.49.0

transformer that is higher than 4.49 don't have sdpa support