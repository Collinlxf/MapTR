# Step-by-step installation instructions

Following https://mmdetection3d.readthedocs.io/en/latest/getting_started.html#installation



**a. Create a conda virtual environment and activate it.**
```shell
conda create -n maptr python=3.8 -y
conda activate maptr
```

**b. Install PyTorch and torchvision following the [official instructions](https://pytorch.org/).**
```shell
pip install torch==1.9.1+cu111 torchvision==0.10.1+cu111 torchaudio==0.9.1 -f https://download.pytorch.org/whl/torch_stable.html
# Recommended torch>=1.9
```

**c. Install gcc>=5 in conda env (optional).**
```shell
conda install -c omgarcia gcc-5 # gcc-6.2
```

**c. Install mmcv-full.**
<!-- MMCV 是一个面向计算机视觉的基础库，它支持了很多开源项目，类似于opencv只是mmcv提供了与深度学习紧密结合的工具 -->
```shell
pip install mmcv-full==1.4.0
#  pip install mmcv-full==1.4.0 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9.0/index.html
```

**d. Install mmdet and mmseg.**
<!-- MMDetection 是一个由OpenMMLab 开发的开源目标检测工具箱，基于PyTorch 实现。 该库提供了丰富的目标检测算法，包括经典的Faster R-CNN、YOLO 和最新的一些研究成果，非常方便于研究者和工程师进行模型的训练和推理 -->
<!-- MMSegmentation 是一个工具箱，它为语义分割任务的统一实现和模型评估提供了一个框架，并且高质量实现了常用的语义分割方法和数据集。 MMSeg 主要包含了apis, structures, datasets, models, engine, evaluation 和visualization 这七个主要部分。 -->
```shell
pip install mmdet==2.14.0
pip install mmsegmentation==0.14.1
```

**e. Install timm.**
<!-- timm ，也称为pytorch-image-models，是一个开源的集合，包含最先进的PyTorch 图像模型、预训练权重以及用于训练、推理和验证的实用脚本。 -->
```shell
pip install timm
```


**f. Clone MapTR.**
```
git clone https://github.com/hustvl/MapTR.git
```

**g. Install mmdet3d and GKT**
```shell
cd /path/to/MapTR/mmdetection3d
python setup.py develop

cd /path/to/MapTR/projects/mmdet3d_plugin/maptr/modules/ops/geometric_kernel_attn
python setup.py build install

```

**h. Install other requirements.**
```shell
cd /path/to/MapTR
pip install -r requirement.txt
```

**i. Prepare pretrained models.**
<!-- 下载的是Backbone ResNet-50和ResNet-18 -->
```shell
cd /path/to/MapTR
mkdir ckpts

cd ckpts 
wget https://download.pytorch.org/models/resnet50-19c8e357.pth
wget https://download.pytorch.org/models/resnet18-f37072fd.pth
```

