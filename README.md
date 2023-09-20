# Bert-VITS2

VITS2 Backbone with bert
## 本项目fork自[Stardust-minus/Bert-VITS2](https://github.com/fishaudio/Bert-VITS2)
## 严禁将此项目用于一切违反《中华人民共和国宪法》，《中华人民共和国刑法》，《中华人民共和国治安管理处罚法》和《中华人民共和国民法典》之用途。
## 严禁用于任何政治相关用途
### Video:https://www.bilibili.com/video/BV1hp4y1K78E
### Demo:https://www.bilibili.com/video/BV1TF411k78w
### 本地部署指导视频：https://www.bilibili.com/video/BV18N4y1Q7JK

## 本地部署
### 1.安装相应python,cuda,cudnn,pytorch(gpu)和对应的依赖(自行寻找教程）
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
#### 1.3 

## References
+ [anyvoiceai/MassTTS](https://github.com/anyvoiceai/MassTTS)
+ [jaywalnut310/vits](https://github.com/jaywalnut310/vits)
+ [p0p4k/vits2_pytorch](https://github.com/p0p4k/vits2_pytorch)
+ [svc-develop-team/so-vits-svc](https://github.com/svc-develop-team/so-vits-svc)
+ [PaddlePaddle/PaddleSpeech](https://github.com/PaddlePaddle/PaddleSpeech)
