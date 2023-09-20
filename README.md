# Bert-VITS2

VITS2 Backbone with bert
## 本项目fork自[Stardust-minus/Bert-VITS2](https://github.com/fishaudio/Bert-VITS2)
## 严禁将此项目用于一切违反《中华人民共和国宪法》，《中华人民共和国刑法》，《中华人民共和国治安管理处罚法》和《中华人民共和国民法典》之用途。
## 严禁用于任何政治相关用途
### Video:https://www.bilibili.com/video/BV1hp4y1K78E
### Demo:https://www.bilibili.com/video/BV1TF411k78w
### 本地部署指导视频：https://www.bilibili.com/video/BV18N4y1Q7JK
### 数据预处理打标视频：https://www.bilibili.com/video/BV1B841197Em https://www.bilibili.com/video/BV1uz4y1j7q7

## 本地部署
### 1.安装相应python,cuda,cudnn,pytorch(gpu)(自行寻找教程），下载对应依赖和模型包
#### 1.1 可以使用虚拟环境，在虚拟环境安装torch，在终端将requirements.txt里的依赖进行安装：
```python
pip install -r requirements.txt
```

#### 在终端验证torch版本是否正确：
```python
pip list
```
![屏幕截图 2023-09-20 115825](https://github.com/Pruokai/Bert-VITS2/assets/119948347/246483f7-c01c-486c-8949-7db5f0678b04)

#### 1.2 到[hugging face](https://huggingface.co/)下载对应的bert模型到bert文件里，[中文](https://huggingface.co/hfl/chinese-roberta-wwm-ext-large)，[日文](https://huggingface.co/cl-tohoku/bert-base-japanese-v3/tree/main)，对照一下，把带LFS后缀的或者说缺失的下载下来。
#### 1.3 验证模型是否工作正常，打开text文件夹下的chinese_bert.py、japanese.py和japanese_bert.py，将代码中的路径修改为下载的对应的中日文的bert模型目录，运行尝试一下，print出1024日志，说明是正常的。
#### 1.4 下载[底模](https://openi.pcl.ac.cn/Stardust_minus/Bert-VITS2/modelmanage/model_filelist_tmpl?name=Bert-VITS2%E5%BA%95%E6%A8%A1)，新建logs文件夹，在logs文件夹下新建一个文件夹（自行命名），放入文件夹。

### 2. 数据集收集与处理
#### 2.1 数据集收集，获取你想要克隆的人物角色的音频
#### 2.2 进行预处理，去除噪声，背景音乐，分段并打标，新建raw文件夹，在raw文件夹下创建一个新文件夹，自行命名，然后将处理后音频文件放入其中，再将打标生成的.list文件放入filelists文件夹下，修改成对应的名字。
#### 2.3 clean原始文案，打开preprocess_text.py，将
```python
 default="filelists/genshin.list",
```
#### 里的路径进行修改，然后运行。
#### 2.4 重采样，打开resample.py，运行。
#### 2.5 生成bert相关信息，打开bert_gen.py，根据电脑配置修改
```python
   parser.add_argument("--num_processes", type=int, default=2)
```
#### 里面的数字以提高速度，运行，如果报错，查看
```python
    if hps.data.add_blank:
```
#### 修改为：
```python
    if True:
```
### 3.开始训练
#### 3.1 打开configs文件夹下的config.json文件，根据配置修改epochs与batch_size，
#### 3.2 在终端开始训练
```python
py .\train_ms.py -m YourModelName -c configs/config.json
```
### 4.推理
#### 4.1 打开webui.py，修改
```python
     "-m", "--model", default="./logs/as/G_8000.pth", help="path of your model"
```
#### 为你logs目录下的模型文件，运行。

## References
+ [anyvoiceai/MassTTS](https://github.com/anyvoiceai/MassTTS)
+ [jaywalnut310/vits](https://github.com/jaywalnut310/vits)
+ [p0p4k/vits2_pytorch](https://github.com/p0p4k/vits2_pytorch)
+ [svc-develop-team/so-vits-svc](https://github.com/svc-develop-team/so-vits-svc)
+ [PaddlePaddle/PaddleSpeech](https://github.com/PaddlePaddle/PaddleSpeech)
