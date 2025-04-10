# 🧠 Handwritten Digit Recognition with PyTorch 🖋️🔥

Welcome to the **MNIST Digit Classifier** project! 🎉  
This repository contains a simple yet powerful Convolutional Neural Network (CNN) built using **PyTorch** to classify handwritten digits from the **MNIST** dataset.  
Plus, you can test it on your own custom images! 🖼️✨

---
🧠 Requirements
torch

torchvision

numpy

pillow

```
pip install torch torchvision numpy pillow
```

## 🚀 Features

- 📦 Train a CNN model on the MNIST dataset
- 🧠 Achieve over **99% accuracy** on training data
- 📷 Predict digits from custom images
- 💾 Save and reload the trained model
- 🧪 Uses PyTorch, TorchVision, and PIL

---

## 🛠️ Installation

```bash
git clone https://github.com/your-username/mnist-cnn-pytorch.git
cd mnist-cnn-pytorch
pip install -r requirements.txt
```

🧱 Model Architecture Explanation:
Here's a look at the Convolutional Neural Network (CNN) used in this project:
```
self.network = nn.Sequential(
    nn.Conv2d(in_channels=1, out_channels=32, kernel_size=3),   # Output: 32 x 26 x 26
    nn.ReLU(),
    nn.Conv2d(32, 64, kernel_size=3),                           # Output: 64 x 24 x 24
    nn.ReLU(),
    nn.Conv2d(64, 64, kernel_size=3),                           # Output: 64 x 22 x 22
    nn.ReLU(),
    nn.Flatten(),
    nn.Linear(64 * 22 * 22, 10)                                 # Final output layer (10 classes)
)
```

Conv2d: Applies a 2D convolution to the input image.

ReLU: Adds non-linearity.

Flatten: Converts the 3D output to 1D for the fully connected layer.

Linear: Final layer mapping to the 10 digit classes (0–9).

📏 Note: After three 3x3 conv layers (without padding), the 28x28 input becomes 22x22 due to shrinking:

28 → 26 → 24 → 22

🏃‍♂️ Training
The model is trained for 10 epochs using:

✅ CrossEntropyLoss

⚡ Adam Optimizer

📈 Batch size of 32


🔮 Inference
You can test your own handwritten digit images using the function:

predict_image('path_to_image.jpg')
Make sure the image is:

Grayscale (1 channel)

28x28 pixels 🖼️

White digit on a black background (like MNIST)
