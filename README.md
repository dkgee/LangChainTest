# LangChainTest


```shell
pip install chromadb
pip install -U python-dotenv
pip install -U langchain
pip install -U torch
pip install openai
```

#### 遇到huggingface模型下载报错，代码中设置本地代理可解决

```python
import os
os.environ["http_proxy"] = "http://127.0.0.1:10809"
os.environ["https_proxy"] = "http://127.0.0.1:10809"
```


# audio-dev

## 项目说明
该项目用于将音频转换为文本，主要使用PaddleSpeech。基本时长

注意：目前只支持WAV格式,它要求音频文件的采样率是16000Hz，如果输入的文件不符合要求，根据提示按y后，程序会自动将音频文件调整成它能识别的样子，然后给出识别结果。

1. [百度飞桨PaddleSpeech的简单使用](https://blog.csdn.net/fj_changing/article/details/127919586)

#### 环境安装

```shell
conda create -n paddleaudio python=3.9
pip install paddlepaddle -i https://mirror.baidu.com/pypi/simple
pip install pytest-runner
pip install paddlespeech
pip install opencv-python -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install numpy==1.21.6
pip install ppdiffusers==0.14.2
pip install opencv-python==4.7.0.72 paddlenlp==2.5.2 paddlepaddle==2.4.1

```

#### 代码

```python

from paddlespeech.cli.asr.infer import ASRExecutor
asr = ASRExecutor()
# result = asr(audio_file="data/zh.wav")
# print(result)
# 我认为跑步最重要的就是给我带来了身体健康

# 短视频下载方式
# lux https://www.douyin.com/video/7250104510733978941

# 输入的音频必须是wav格式，大小在16kb以内
# 它要求音频文件的采样率是16000Hz，如果输入的文件不符合要求，根据提示按y后，程序会自动将音频文件调整成它能识别的样子，然后给出识别结果。

# 提取短视频中的音频
# ffmpeg -i input.mp4 -ac 1 -ar 16000 -b:a 16k -f wav test01.wav

# 存在的问题：1、遇到一些口语方言会识别错误。识别后还需要人工矫正。

# result = asr(audio_file="data/3thd-3.wav")
result = asr(audio_file="data/test01.wav")
print(result)

```