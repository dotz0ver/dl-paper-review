# 🧠 (AlexNet) ImageNet Classification with Deep Convolutional Neural Networks (2012)

This folder contains a reproduction of the **AlexNet** model from the landmark paper:

> **ImageNet Classification with Deep Convolutional Neural Networks**  
> by Alex Krizhevsky, Ilya Sutskever, Geoffrey E. Hinton  
> Published in NIPS 2012

---

## 🔗 Links

- 📄 **Paper**: [ImageNet Classification with Deep CNNs (NIPS 2012)](https://papers.nips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)
- ✍️ **My Review**: [Paper Review](https://dotz0ver.tistory.com/45)
- 🧪 **Implementation Notebook**: [`Vision/Alexnet/alexnet.ipynb`](./Vision/Alexnet/alexnet.ipynb)

---

## 📝 Description

This implementation reproduces the original **AlexNet architecture** as described in the paper, using **CIFAR-10** as the dataset for training and evaluation.  
Although AlexNet was originally designed for ImageNet-scale data, this reproduction adapts it to CIFAR-10 for practicality and ease of experimentation.  
10-Crop testing is used for final evaluation, as described in the original paper.

Implemented features include:

- 🧠 **Model architecture**
  - 8-layer AlexNet structure (5 convolutional + 3 fully connected layers)
  - ReLU activations
  - Local Response Normalization (LRN)
  - Dropout regularization

- 🎛️ **Training & optimization**
  - Training split across 2 GPUs (layer-wise parallelism)
  - Overlapping max pooling (stride 2, kernel size 3)

- 🧪 **Evaluation setup**
  - Data augmentation (e.g., random crops, flips)
  - Top-1 accuracy evaluated via 10-Crop testing
