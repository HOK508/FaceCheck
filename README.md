<p align="center">
    <img src="pics/logo.png" width="300"/>
</p>

<p align="center">  
    <a href="https://github.com/HOK508/FaceCheck">
        <img alt="GitHub" src="https://img.shields.io/github/stars/yourusername/FaceCheck?style=social">
    </a>
    <a href="https://github.com/HOK508/FaceCheck/blob/main/LICENSE">
        <img alt="License" src="https://img.shields.io/github/license/yourusername/FaceCheck">
    </a>
</p>

<p align="center">
    <b> English | <a href="README_CN.md">简体中文</a> </b>
</p>

# FaceCheck
**AI生成图像鉴别系统（真实 vs AI生成人脸二分类）**

FaceCheck 是一个用于区分 **真实人脸** 与 **AI生成人脸** 的深度学习二分类识别系统。  
它实现了从 **数据预处理、模型训练、注意力机制增强、对比学习、性能评估、可视化** 到 **Web部署** 的完整深度学习工作流，适用于学术研究、课程作业及工程应用。

---

## 模型结构
```text
FaceCheck/
├─ data/                  # Dataset (real and AI-generated faces)
├─ configs/               # Model configuration files
├─ checkpoints/           # Model checkpoints
├─ src/                   # Training and evaluation scripts
│   ├─ train.py
│   ├─ evaluate.py
│   ├─ predict.py
├─ web_app.py             # Web frontend entry point
├─ requirements.txt       # Python dependencies
├─ README.md
└─ pics/                  # Logo and demo images
```


## 核心功能

- **数据处理**：混合数据集加载、图像归一化、数据增强（翻转、裁剪等）  
- **模型训练**：基于 ResNet 等深度学习模型的二分类训练  
- **特征增强**：注意力机制提升关键区域特征聚合，对比学习增强判别能力  
- **模型评估**：支持准确率、精确率、召回率、F1-score 等指标计算及可视化  
- **可视化**：Grad-CAM 等方法展示模型关注区域  
- **Web部署**：简单易用的可视化前端，支持在线图片检测  

---

## 项目特点

- **完整流程**：涵盖数据处理、模型训练、特征优化、性能评估、Web应用  
- **高可扩展性**：可替换网络骨架、增强方法及对比学习策略  
- **易于复现**：提供详细训练脚本和配置文件，适合深度学习课程或科研实验  
- **前沿技术**：融合注意力机制与对比学习，提高 AI生成图像检测的鲁棒性  

---

## 快速开始 (Quick Start)

### 1. 克隆仓库
```bash
git clone https://github.com/yourusername/FaceCheck.git
cd FaceCheck
```

### 2. 创建环境
```bash
conda create -n facecheck python=3.8
conda activate facecheck
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124
pip install -r requirements.txt
```

### 3. 模型训练
```bash
python train.py --config configs/resnet_attention.yaml
```

### 4. 模型评估
```bash
python evaluate.py --model checkpoints/resnet_attention.pth --test_dir data/test
```
