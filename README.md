# 🎨 Neural Style Transfer (NST)

> **Transform any photo into a work of art** — blend the content of one image with the artistic style of another using deep learning.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 Overview

Neural Style Transfer (NST) is a deep learning technique that takes two images — a **content image** and a **style image** — and generates a new image that preserves the structure of the content image while adopting the visual texture and artistic style of the style image.

This project implements NST from scratch using a pre-trained **VGG-19** convolutional network, based on the seminal paper by **Gatys et al. (2015)**: [*A Neural Algorithm of Artistic Style*](https://arxiv.org/abs/1508.06576).

### How it works

The algorithm works by defining two loss functions:

- **Content Loss** — ensures the high-level structure (objects, shapes) of the content image is preserved in the output.
- **Style Loss** — matches the texture/style patterns of the style image across multiple layers of the network using Gram matrices.

The generated image is iteratively updated to minimize the combined weighted loss, producing a stylized result.

---

## ✨ Demo

### Example 1

| Content Image | Style Image | Generated Output |
|:---:|:---:|:---:|
| <img src="Demo_IO_Images/i-p/i_p%20image.jpg" width="250"> | <img src="Demo_IO_Images/i-p/style%201.png" width="250"> | <img src="Demo_IO_Images/o-p/o_p%20style%201.jpg" width="250"> |

### Example 2

| Content Image | Style Image | Generated Output |
|:---:|:---:|:---:|
| <img src="Demo_IO_Images/i-p/i_p%20image.jpg" width="250"> | <img src="Demo_IO_Images/i-p/style%202.jpg" width="250"> | <img src="Demo_IO_Images/o-p/o_p%20style%202.jpg" width="250"> |

> Demo images are available in the `Demo_IO_Images/` folder.

---

## 🗂️ Project Structure

```text
ArtifyAI/
│
├── NST_Code/               # Core NST implementation files
├── Demo_IO_Images/         # Sample input/output images
├── code.ipynb              # Main Jupyter Notebook with full pipeline
├── requirements.txt
├── .gitignore
└── README.md
```

---


---

## 🚀 Getting Started

### Prerequisites

Make sure you have Python 3.8+ and the following packages installed:

```bash
pip install tensorflow numpy matplotlib Pillow
```

Or install all dependencies at once:

```bash
pip install -r requirements.txt
```

### Running the Notebook

1. **Clone the repository**

   ```bash
   git clone https://github.com/samriddha1bits-ship-it/ArtifyAI.git
   cd ArtifyAI
   ```

2. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook code.ipynb
   ```

3. **Set your images**

   Inside the notebook, update the paths to your content and style images:

   ```python
   content_path = 'path/to/your/content_image.jpg'
   style_path   = 'path/to/your/style_image.jpg'
   ```

4. **Run all cells** and watch your stylized image come to life! 🎨

---

## ⚙️ Key Parameters

| Parameter | Description | Default |
|---|---|---|
| `content_weight` | Weight for content loss | `1e4` |
| `style_weight` | Weight for style loss | `1e-2` |
| `epochs` | Number of optimization iterations | `10` |
| `steps_per_epoch` | Steps per epoch | `100` |
| `learning_rate` | Adam optimizer learning rate | `0.02` |

Tweak `style_weight` vs `content_weight` to control how painterly vs realistic the output looks.

---

## 🧠 Model Architecture

The implementation uses **VGG-19** pretrained on ImageNet:

- **Content representation** is extracted from layer: `block5_conv2`
- **Style representation** is extracted from layers: `block1_conv1`, `block2_conv1`, `block3_conv1`, `block4_conv1`, `block5_conv1`

Style is captured using **Gram matrices** of feature map activations, which encode texture information independent of spatial layout.

---
---

## 🔮 Future Improvements

- Real-time style transfer
- Multiple style blending
- Streamlit web application
- Support for higher-resolution images
- Faster optimization techniques

---

## 📚 References

- Gatys, L. A., Ecker, A. S., & Bethge, M. (2015). [A Neural Algorithm of Artistic Style](https://arxiv.org/abs/1508.06576). *arXiv:1508.06576*
- [TensorFlow NST Tutorial](https://www.tensorflow.org/tutorials/generative/style_transfer)
- [VGG-19 Paper — Very Deep Convolutional Networks](https://arxiv.org/abs/1409.1556)

---

## 👨‍💻 Author

**Samriddha Banerjee**

[![GitHub](https://img.shields.io/badge/GitHub-Samriddha--Banerjee-black?logo=github)](https://github.com/samriddha1bits-ship-it)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Samriddha--Banerjee-blue?logo=linkedin)](https://www.linkedin.com/in/samriddha-banerjee-a077b1316/)

---