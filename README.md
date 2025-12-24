🍎 Fresh Fruit Image Classification using CNN (PyTorch)
📌 Assignment: CNN Image Classification with Real-World Testing

Course: Deep Learning / Computer Vision
Framework: PyTorch
Dataset Type: Fresh Fruit (RGB Images)

📖 Project Overview

This project implements a Convolutional Neural Network (CNN) using PyTorch to classify fresh fruit images.
Although the assignment required a minimum of 3 fruit classes, a 10-class Fresh Fruit dataset was used to improve model robustness and generalization.

The project demonstrates a complete deep learning pipeline, including:

Dataset loading and preprocessing

CNN model design

Training and evaluation

Confusion matrix heatmap

Visual error analysis

Real-world prediction using smartphone images

All steps are fully automated and runnable using “Run All” in Google Colab.

🍓 Dataset Description
📂 Fruit Classes (10)

Apple

Banana

Avocado

Cherry

Kiwi

Mango

Orange

Pineapple

Strawberries

Watermelon

📁 Dataset Structure
Model/
├── train/
│   ├── Apple/
│   ├── Banana/
│   ├── avocado/
│   ├── cherry/
│   ├── kiwi/
│   ├── mango/
│   ├── orange/
│   ├── pinenapple/
│   ├── strawberries/
│   └── watermelon/
├── test/
│   ├── Apple/
│   ├── Banana/
│   └── ...

📸 Custom Images

10 real-world images captured using a smartphone

Stored in the Custom/ directory

Used for final prediction and confidence scoring

🔄 Data Preprocessing

The following preprocessing steps were applied:

Resize images to 128 × 128

Convert images to PyTorch tensors

Normalize using ImageNet statistics

transforms.Resize((128,128))
transforms.ToTensor()
transforms.Normalize(mean=[0.485,0.456,0.406],
                     std=[0.229,0.224,0.225])

🧠 CNN Model Architecture

The CNN consists of:

3 Convolutional blocks

Conv2D → ReLU → MaxPooling

Fully connected classifier

Dense → ReLU → Dropout

Output layer with 10 neurons

🔧 Architecture Summary
Input Image (3 × 128 × 128)
↓
Conv2D (32) + ReLU + MaxPool
↓
Conv2D (64) + ReLU + MaxPool
↓
Conv2D (128) + ReLU + MaxPool
↓
Fully Connected (256)
↓
Output Layer (10 classes)

⚙️ Training Configuration

Loss Function: CrossEntropyLoss

Optimizer: Adam

Learning Rate: 0.0005

Epochs: 25

Batch Size: 32

📈 Training Performance
🔹 Training Loss vs Epochs

🔹 Training Accuracy vs Epochs
<img width="1153" height="532" alt="image" src="https://github.com/user-attachments/assets/774d613c-0a2e-40c0-a5e1-bd13255e18e1" />


The model shows stable convergence with increasing accuracy over epochs.

🔥 Confusion Matrix Heatmap
The confusion matrix below illustrates classification performance across all 10 fruit classes on the test set.
<img width="964" height="825" alt="image" src="https://github.com/user-attachments/assets/5c36fe8b-0f7d-4ac4-a98f-83fde7af246d" />




Strong diagonal dominance indicates high classification accuracy

Minor confusion occurs between visually similar fruits

❌ Visual Error Analysis

Below are three randomly selected misclassified test images, showing the true label vs predicted label.

This analysis helps understand:

Class overlap

Visual ambiguity

Dataset limitations

📸 Real-World Prediction (Custom Images)

The trained model was tested on real-world smartphone images.

Each image displays:
<img width="1000" height="510" alt="image" src="https://github.com/user-attachments/assets/5fed536a-13b2-4d39-8ed6-2f7dacaac66b" />


Predicted fruit class

Confidence score (%)

Example output:
<img width="855" height="311" alt="image" src="https://github.com/user-attachments/assets/b8d8b5d3-cde7-4a2c-9e84-5b3e389f71d6" />


Predicted: Mango (97.6%)

💾 Saved Model

The trained model is saved for reproducibility:

Model/fresh_fruit_10class_cnn.pth

▶️ How to Run (Google Colab)

Open the notebook (210129.ipynb)

Select Runtime → Run all

The notebook will:

Load dataset automatically

Train the CNN

Generate plots and heatmaps

Predict custom images with confidence

⚠️ No manual uploads required.
