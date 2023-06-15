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