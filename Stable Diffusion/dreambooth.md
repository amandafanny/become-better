## windows

The commands you need to execute with order to downgrade CUDA

[https://gist.github.com/FurkanGozukar](https://gist.github.com/FurkanGozukara/e2db853d2016a4a9ae2cc32dc41d730a)

```
1:
activate

2:
pip uninstall torch torchvision

3:
pip uninstall torchaudio

4:
pip uninstall xformers

run steps either 5 or 6 - not both at the same time. 5 is older version, 6 is new version. join discord and ask if you cant be sure
discord : https://discord.com/servers/software-engineering-courses-secourses-772774097734074388

5:
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu116

5: this is downgrade. alternatively you can upgrade by following below
pip install -U -I --no-deps https://github.com/C43H66N12O12S2/stable-diffusion-webui/releases/download/torch13/xformers-0.0.14.dev0-cp310-cp310-win_amd64.whl

6: this is upgrade this works too beta 0.0.17 and cuda to 117
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu117

6: this is upgrade this works too beta 0.0.17
pip install xformers==0.0.17.dev465
```

These below are specific hashes used in video but not necessary to use. You can install newest version of both DreamBooth and Automatic1111 and just downgrade CUDA with the above commands.
Automatic 1111 commit : dc8d1f4f8beb546089abd107db3432e03339c9c0
Dreambooth commit : c544ee11aee0085a7fbb7fdda65898dea2145f0c

### RunPod

Upgrade xformers Commands

```
https://www.youtube.com/@SECourses

1:
pip uninstall torch torchvision

2:
pip uninstall torchaudio

3:
pip uninstall xformers

4:
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu116

5: pip install xformers==0.0.17.dev465
```

## 杀掉进程

```
fuser -k 3000/tcp
```

### 启动进程

[参考链接](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings)

```
python launch.py --xformers --enable-insecure-extension-access --ngrok 2MxfiPkPEYhXZZbvaOk1orA1KIQ_6zqmX6UFjnso8u1P6M7sU --gradio-queue --share  --gradio-auth a:a --api-log --api
```

```
accelerate==0.16.0
albumentations~=1.3.0
bitsandbytes==0.35.4
diffusers==0.13.1
gitpython~=3.1.31
fastapi
ftfy~=6.1.1
modelcards~=0.1.6
tensorboard
tensorflow==2.11.0; sys_platform != 'darwin' or platform_machine != 'arm64'
tensorflow-macos==2.11.0; sys_platform == 'darwin' and platform_machine == 'arm64'
mediapipe-silicon; sys_platform == 'darwin'
mediapipe; sys_platform != 'darwin'
tqdm~=4.64.1
transformers~=4.26.1
discord-webhook~=1.1.0
lion-pytorch~=0.0.7
xformers==0.0.17.dev464
```

### 报错

```
Launching Web UI with arguments: --port 3010 --xformers --listen --enable-insecure-extension-access --share --gradio-auth a:a
2023-03-14 15:47:48.578871: I tensorflow/core/platform/cpu_feature_guard.cc:193] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  AVX2 FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
2023-03-14 15:47:49.300171: W tensorflow/compiler/xla/stream_executor/platform/default/dso_loader.cc:64] Could not load dynamic library 'libnvinfer.so.7'; dlerror: libnvinfer.so.7: cannot open shared object file: No such file or directory; LD_LIBRARY_PATH: /workspace/stable-diffusion-webui/venv/lib/python3.10/site-packages/cv2/../../lib64:
2023-03-14 15:47:49.300263: W tensorflow/compiler/xla/stream_executor/platform/default/dso_loader.cc:64] Could not load dynamic library 'libnvinfer_plugin.so.7'; dlerror: libnvinfer_plugin.so.7: cannot open shared object file: No such file or directory; LD_LIBRARY_PATH: /workspace/stable-diffusion-webui/venv/lib/python3.10/site-packages/cv2/../../lib64:
2023-03-14 15:47:49.300270: W tensorflow/compiler/tf2tensorrt/utils/py_utils.cc:38] TF-TRT Warning: Cannot dlopen some TensorRT libraries. If you would like to use Nvidia GPU with TensorRT, please make sure the missing libraries mentioned above are installed properly.
SD-Webui API layer loaded
Loading weights [4c86efd062] from /workspace/stable-diffusion-webui/models/Stable-diffusion/SDv1-5.ckpt
Creating model from config: /workspace/stable-diffusion-webui/configs/v1-inference.yaml
LatentDiffusion: Running in eps-prediction mode
DiffusionWrapper has 859.52 M params.
Applying xformers cross attention optimization.
Textual inversion embeddings loaded(0):
Model loaded in 36.1s (load weights from disk: 0.9s, create model: 8.3s, apply weights to model: 18.8s, apply half(): 6.3s, load VAE: 1.4s, move model to device: 0.3s).
Traceback (most recent call last):
  File "/workspace/stable-diffusion-webui/venv/lib/python3.10/site-packages/gradio/networking.py", line 119, in start_server
    s.bind((LOCALHOST_NAME, server_port))
OSError: [Errno 98] Address already in use

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/workspace/stable-diffusion-webui/launch.py", line 361, in <module>
    start()
  File "/workspace/stable-diffusion-webui/launch.py", line 356, in start
    webui.webui()
  File "/workspace/stable-diffusion-webui/webui.py", line 218, in webui
    app, local_url, share_url = shared.demo.launch(
  File "/workspace/stable-diffusion-webui/venv/lib/python3.10/site-packages/gradio/blocks.py", line 1374, in launch
    server_name, server_port, local_url, app, server = networking.start_server(
  File "/workspace/stable-diffusion-webui/venv/lib/python3.10/site-packages/gradio/networking.py", line 122, in start_server
    raise OSError(
OSError: Port 3010 is in use. If a gradio.Blocks is running on the port, you can close() it or gradio.close_all().
Relauncher: Process is ending. Relaunching in 2s...
```

## 使用升级版

### 进入插件目录

```
pip install --upgrade --no-deps --force-reinstall -r requirements.txt
```

## 分支

```
43ae9d5
c544ee1
```
