# [RK-Net]Joint Representation Learning and Keypoint Detection for Cross-view Geo-localization
![Python 3.6](https://img.shields.io/badge/python-3.6-green.svg)


## Prerequisites

- Python 3.6
- GPU Memory >= 8G
- Numpy > 1.12.1
- Pytorch 0.3+
- scipy == 1.2.1
- [Optional] apex (for float16) [Requirements](https://github.com/NVIDIA/apex#requirements) & [Quick Start](https://github.com/NVIDIA/apex#quick-start)

## Getting started
### Installation
- Install Pytorch from http://pytorch.org/
- Install Torchvision from the source
```
git clone https://github.com/pytorch/vision
cd vision
python setup.py install
```
- [Optinal] You may skip it. Install apex from the source
```
git clone https://github.com/NVIDIA/apex.git
cd apex
python setup.py install --cuda_ext --cpp_ext
```

## Dataset & Preparation
Download [University-1652](https://github.com/layumi/University1652-Baseline) upon request and put them under the `./data/` folder. You may use the request [template](https://github.com/layumi/University1652-Baseline/blob/master/Request.md).


## Demo
```python
import torch
from model import USAM

input = torch.randn(128, 512, 16, 16)
usam = USAM()
output = usam(input)
print(output.shape)

```


## Train & Evaluation
### Train & Evaluation University-1652
```
python train.py --name RK-Net --share --extra --stride 1 --fp16; 
python test.py --name RK-Net
```

Default setting: Drone -> Satellite

## Trained Model

You could download the trained model at [GoogleDrive](https://drive.google.com/drive/folders/149Df_WXEqw7jp9de6IYn7f2Jgn1cJf6D?usp=sharing). After download, please put model folders under `./model/`.

## Citation

```bibtex
@article{lin2022,
  title={Joint Representation Learning and Keypoint Detection for Cross-view Geo-localization},
  author={Lin, Jinliang and Zheng, Zhedong and Zhong, Zhun and Luo, Zhiming and Li, Shaozi and Yang, Yi and Sebe, Nicu},
  journal={IEEE Transactions on Image Processing (TIP)},
  year={2022},
  }
}
```

```bibtex
@article{zheng2020university,
  title={University-1652: A Multi-view Multi-source Benchmark for Drone-based Geo-localization},
  author={Zheng, Zhedong and Wei, Yunchao and Yang, Yi},
  journal={ACM Multimedia},
  year={2020}
}
```
