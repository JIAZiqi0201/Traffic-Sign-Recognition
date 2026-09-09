# Traffic-Sign-Recognition
📖 Overview
This project implements a Convolutional Neural Network (CNN) to classify traffic signs into 5 categories. The model takes a single traffic sign image as input and predicts which class it belongs to, simulating real-world applications in autonomous driving and advanced driver-assistance systems (ADAS).

🎯 Classification Problem
Classify traffic sign images into 5 categories:

Class	Description
0	Speed limits (e.g., 30 km/h, 50 km/h)
1	Warning signs
2	Mandatory actions
3	Prohibitory signs
4	Other signs
🧠 Hierarchical Approach
Level	Method	Type	Description
1	Data Preprocessing	Pipeline	Normalization + One-Hot Encoding
2	Train-Test Split	Custom	75/25 train-validation split
3	Conv2D Layer	Supervised	Extract spatial features from images
4	MaxPooling2D	Supervised	Downsample feature maps
5	Dense Layer	Supervised	Fully connected classification layer
6	Model Checkpoint	Callback	Save best model based on validation accuracy
7	Evaluation	Metric	Accuracy + Loss monitoring
🏗️ Architecture
text
Complete implementation
│
├── Task 1: Data Split (2.5 pts)
│   └── 75/25 train-validation split + shuffle
│
├── Task 2: Build CNN Model (7.5 pts)
│   ├── Conv2D (32 filters, 3x3) + BatchNorm + ReLU
│   ├── MaxPool2D (2x2) + Dropout (0.25)
│   ├── Conv2D (64 filters, 3x3) + BatchNorm + ReLU
│   ├── MaxPool2D (2x2) + Dropout (0.25)
│   ├── Flatten
│   ├── Dense (256) + BatchNorm + ReLU + Dropout (0.5)
│   └── Dense (5) + Softmax
│
├── Data Pipeline
│   ├── prepare_dataset()     # Load + resize (30x30) + numpy conversion
│   └── train_test_split()    # Random seed = 1
│
├── Training
│   ├── Optimizer: Adam
│   ├── Loss: Categorical Crossentropy
│   ├── Epochs: 30
│   └── Callbacks: ModelCheckpoint
│
├── Visualization
│   ├── Sample images per class
│   ├── Training/Validation loss curves
│   └── Training/Validation accuracy curves
│
└── Evaluation (Accuracy Thresholds: 70% / 80% / 95%)
