
<p align="center">  
    <a href="https://github.com/HOK508/FaceCheck">
        <img alt="GitHub" src="https://github.com/HOK508/FaceCheck/blob/main/FaceCheck.jpg">
    </a>

<p align="center">
    <a href="https://github.com/HOK508/FaceCheck/blob/main/LICENSE">
        <img alt="License" src="https://img.shields.io/github/license/HOK508/FaceCheck">
    </a>
    <img alt="Python" src="https://img.shields.io/badge/Python-3.8+-blue">
    <img alt="Framework" src="https://img.shields.io/badge/PyTorch-2.x-red">
    <img alt="Task" src="https://img.shields.io/badge/Task-AI%20Face%20Detection-brightgreen">
</p>


<p align="center">
    <b> English | <a href="README_CN.md">简体中文</a> </b>
</p>




# FaceCheck
**AI生成图像鉴别系统（真实 vs AI生成人脸二分类）**

FaceCheck 是一个用于区分 **真实人脸** 与 **AI生成人脸** 的深度学习二分类识别系统。  
它实现了从 **数据预处理、模型训练、注意力机制增强、对比学习、性能评估、可视化** 到 **界面交互** 的完整深度学习工作流，适用于课程作业。

---

## 模型结构
```text
FaceCheck/
├─ dataset/               
│   ├─ fake/
│   │   ├─ train/
│   │   ├─ test/
│   ├─ real/
│   │   ├─ train/
│   │   ├─ test/              
├─ ckpt/          
├─ src/                 
│   ├─ train.py
│   ├─ test.py
│   ├─ model.py
│   ├─ dataset.py
│   ├─ utils.py
├─ ui.py             
├─ requirements.txt       
├─ README.md
└─ pics/                 
```


## 核心功能

- **数据处理**：混合数据集加载、图像归一化、数据增强（翻转、裁剪等）  
- **模型训练**：基于 ResNet18 深度学习模型的二分类训练  
- **特征增强**：注意力机制提升关键区域特征聚合，对比学习增强判别能力  
- **模型评估**：支持计算准确率、召回率、F1值，绘制混淆矩阵与ROC曲线，直观展示模型性能；使用TensorBoard可视化训练过程，观察损失和准确率变化。
- **交互界面**：简单易用的可视化前端，支持在线图片检测  

---

## 项目特点

- **完整流程**：涵盖数据处理、模型训练、特征优化、性能评估、交互界面应用  
- **高可扩展性**：可替换网络骨架、增强方法及对比学习策略  
- **易于复现**：提供详细训练脚本和配置文件，适合深度学习课程或科研实验  

---

### 数据集准备 (Dataset Prepare)
#### 1. 真实人脸数据集
```bash
git clone https://github.com/suvojit-0x55aa/celebA-HQ-dataset-download.git
```
#### 2. AI生成人脸数据集
```bash
python generate.py \
    --network=/home/a508/AI/fake/ffhq.pkl \
    --seeds=0-4999 \
    --trunc=1 \
    --outdir=/home/a508/AI/fake/out
```

### 快速开始 (Quick Start)

#### 1. 克隆仓库
```bash
git clone https://github.com/yourusername/FaceCheck.git
cd FaceCheck
```

#### 2. 创建环境
```bash
conda create -n facecheck python=3.8
conda activate facecheck
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
pip install -r requirements.txt
```

#### 3. 模型训练
```bash
python train.py --config configs/resnet_attention.yaml
```

#### 4. 模型评估
```bash
python test.py --model checkpoints/resnet_attention.pth --test_dir data/test
```

