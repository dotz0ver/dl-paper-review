# 🧠 VGG-16 (Very Deep Convolutional Networks for Large-Scale Image Recognition, 2014)

This folder contains a reproduction of the **VGG-16** model from the influential paper:

> **Very Deep Convolutional Networks for Large-Scale Image Recognition**  
> by K. Simonyan & A. Zisserman  
> Published by Visual Geometry Group (VGG), University of Oxford, 2014

---

## 🔗 Links

- 📄 **Paper**: [arXiv:1409.1556](https://arxiv.org/abs/1409.1556)
- ✍️ **My Review**: [Paper Review](https://dotz0ver.tistory.com/50)
- 🧪 **Implementation Notebook**: `Vision/VGG/vgg16.ipynb`

---

## 📝 Description

This implementation reproduces the **VGG-16** architecture using the **Tiny ImageNet** dataset for training and evaluation.  
VGG-16 is known for its **depth** (16 learnable layers) and **simplicity**—relying only on 3×3 convolution filters and 2×2 max pooling layers.

---

## 🧠 Model Architecture

- **Input**: 224×224 RGB image  
- **Conv Layers**: 13  
- **FC Layers**: 3  
- **Activation**: ReLU  
- **Kernel Size**: 3×3, stride=1, padding=1 (same padding)  
- **Pooling**: 2×2 Max Pooling, stride=2 (after conv blocks 1~5)  
- **LRN**: ❌ Not used  
- **Dropout**: ✅ Applied to FC layers (p=0.5)  

---

## ⚙️ Training & Optimization

- **Dataset**: Tiny ImageNet (200 classes)  
- **Batch Size**: 128 _(original: 256)_  
- **Epochs**: 20  
- **Loss**: CrossEntropyLoss  
- **Optimizer**: SGD  
  - Learning rate: 0.01  
  - Momentum: 0.9  
  - Weight decay: 5×10⁻⁴  
- **Learning Rate Scheduler**: ReduceLROnPlateau (↓LR if val loss plateaus)

---

## 🧪 Data Augmentation

**Training Transformations**
- Resize → 256  
- Random Crop → 224×224  
- Random Horizontal Flip  
- Color Jitter (brightness, contrast, saturation, hue)  
- Normalization (Tiny ImageNet RGB Mean/Std)

**Validation / Test Transformations**
- Resize → 224  
- Center Crop → 224×224  
- Normalization
