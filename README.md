# 🌈 Hyperspectral Image Classification using GCN (Graph Convolutional Networks)

This project implements a **Graph Convolutional Network (GCN)** for classifying hyperspectral images (HSI) using the **Indian Pines dataset**. The model leverages both **spectral** and **spatial** features by treating pixels as nodes in a graph and learning their relationships to improve classification performance.

## 🚀 Highlights

- 📡 **Dataset:** Indian Pines Hyperspectral Dataset (AVIRIS sensor, 145x145 pixels, 220 spectral bands)
- 🧠 **Model:** Custom-built Graph Convolutional Network (GCN) in PyTorch
- 🧱 **Input Strategy:** Patch-based processing for capturing spatial context
- 🌐 **Graph Construction:** K-nearest neighbors (KNN) or spatial adjacency matrix
- 📊 **Metrics:** Accuracy, class-wise performance, confusion matrix

---

## 📁 Project Structure

📦GCN/<br>
├── indian_pines_corrected.mat # HSI Indian Pines Dataset<br>
├── indian_pines_gt.mat # ground truth<br>
├── minigcnsample30.ipynb # Training + Evaluation pipeline <br>
├── best_gcn_model.pth # model<br>
├── GCNtest.ipynb # Test and run<br>
└── README.md # You're here :)<br>


---

## 🧠 Methodology

### 🔍 Why GCN?
Traditional CNNs struggle with irregular spatial dependencies in HSI data. GCNs operate directly on graph-structured data—perfect for capturing non-Euclidean relationships across pixels in hyperspectral cubes.

### 🏗️ Model Architecture
- Input: Spectral-spatial patch vector
- Layers: GraphConv → ReLU → Dropout → GraphConv → Softmax
- Loss: CrossEntropyLoss
- Optimizer: Adam
- Graph: Adjacency matrix computed using spatial neighborhoods or pixel similarities

---

## 🛠️ Installation

```bash
git clone https://github.com/Ayush-Debnath/GCN.git
```
Run the GCNtest.ipynb file

## 📊 Results
Metric	Value
Overall Acc	&nbsp;&nbsp;97.31%
Avg F1 Score	&nbsp;&nbsp;0.9730
Kappa Score	&nbsp;&nbsp;0.9693

## 🧪 How to Run
Download the Indian Pines .mat file and place it in the GCNtest.ipynb file in the  having the code:
```bash
# Load the dataset
data = scipy.io.loadmat("/content/drive/MyDrive/Indian_pines_corrected.mat")['indian_pines_corrected']
labels = scipy.io.loadmat("/content/drive/MyDrive/Indian_pines_gt.mat")['indian_pines_gt']
```
Run the cells

## 📷 Sample Visualizations
![image](https://github.com/user-attachments/assets/b05cc551-2e5a-47b3-ad05-a07f2f6d6129)
![image](https://github.com/user-attachments/assets/e1785a65-04ee-4814-97e9-7842cc1f1987)
![image](https://github.com/user-attachments/assets/a6b107a7-3542-4505-9d24-838cfba0ccc3)

🤝 Acknowledgements<br>
Indian Pines dataset: https://www.ehu.eus/ccwintco/index.php/Hyperspectral_Remote_Sensing_Scenes#Indian_Pines

Reasearch paper: https://ieeexplore.ieee.org/document/10234379


## 🧠 Author
👨‍💻 Ayush Debnath<br>
Engineering student, AI/ML, data scientist in the making

