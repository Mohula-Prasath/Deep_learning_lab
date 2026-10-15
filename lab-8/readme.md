# CS3807 – Deep Learning Laboratory

## Experiments 8 and 9

**Effect of Attention Type and Attention Position in a Pretrained ResNet50**

### Objective

Study how different attention mechanisms modify a pretrained convolutional neural network and how the position at which attention is inserted influences image classification performance. A single backbone, ResNet50 pretrained on ImageNet, is used throughout, and all models are compared under the same experimental settings.

---

## Additional Analysis

The experiment compares model performance across several studies:

* Baseline ResNet50 without attention

* Channel attention, spatial attention, sequential channel–spatial attention and lightweight self-attention

* Combined channel + spatial + self-attention

* Attention inserted at different positions (P1, P2, P3, P4)

* Single-stage and multi-stage attention

* Attention order (channel → spatial and spatial → channel)

* Spatial attention kernel size (3×3, 5×5, 7×7)

* Additional attention mechanisms: SE, ECA, CBAM and Coordinate Attention

* Test-set performance using accuracy, macro precision, macro recall and macro F1-score

* Model parameter count, attention parameter count and inference time

The analysis includes:

* Training and validation accuracy curves

* Training and validation loss curves

* Bar graphs of accuracy and macro F1-score

* Accuracy vs parameters and macro F1 vs inference time plots

* Confusion matrices for the baseline and the best attention model

* Feature maps before and after attention

* Channel attention weights

* Spatial attention maps

* Self-attention response maps

* Grad-CAM comparison between the baseline and attention models

* Qualitative comparison on correctly and incorrectly classified images

---

## Dataset

The notebook uses the TensorFlow Flowers (`tf_flowers`) dataset.

* **Number of Classes:** 5 (daisy, dandelion, roses, sunflowers, tulips)

* **Input Size:** 224 × 224 × 3

* **Train / Validation / Test Split:** 70% / 15% / 15% (stratified, fixed seed)

* **Preprocessing:** ImageNet ResNet50 preprocessing

* **Data Augmentation:** random horizontal flip, small rotation, random zoom, random translation and mild contrast variation

The same split and the same augmentation strategy are used for every model.

---

## Model Architecture

### ResNet50 Feature Hierarchy

| Stage | Spatial Resolution | Channels | Attention Position |
|---|---|---|---|
| Stem + MaxPool | 56 × 56 | 64 | – |
| conv2_x | 56 × 56 | 256 | P1 |
| conv3_x | 28 × 28 | 512 | P2 |
| conv4_x | 14 × 14 | 1024 | P3 |
| conv5_x | 7 × 7 | 2048 | P4 |

### Classification Model

```text
Input Image (224 × 224 × 3)
        ↓
Data Augmentation
        ↓
ResNet50 (ImageNet pretrained)
        ↓
Attention Module at P1 / P2 / P3 / P4
        ↓
Global Average Pooling
        ↓
Dropout (0.3)
        ↓
Dense (5 neurons, Softmax)
```

### Attention Modules

* **Channel Attention:** global average pooling, two dense layers (reduction ratio 16) and a sigmoid, producing one weight per channel

* **Spatial Attention:** channel-wise average and maximum, a 7×7 convolution and a sigmoid, producing one weight per spatial location

* **Channel + Spatial:** channel attention followed by spatial attention

* **Self-Attention:** lightweight query–key–value attention over spatial positions with a learnable residual scale

* **SE, ECA, CBAM, Coordinate Attention:** additional established mechanisms compared at P3

### Training Configuration

* **Backbone:** ResNet50 pretrained on ImageNet

* **Stage 1:** backbone frozen, 6 epochs, learning rate 0.001

* **Stage 2:** conv5_x unfrozen, 10 epochs, learning rate 0.0001

* **Optimizer:** Adam

* **Loss Function:** Categorical Crossentropy

* **Batch Size:** 32

* **Dropout Rate:** 0.3

* **Random Seed:** 42

The same settings were used for every experiment to provide a controlled comparison.

---

## Experiments

| ID | Description | Position |
|---|---|---|
| A0 | Baseline (no attention) | – |
| A1 | Channel attention | P3 |
| A2 | Spatial attention | P3 |
| A3 | Channel + Spatial | P3 |
| A4 | Self-attention | P3 |
| A5 | Combined (Channel + Spatial + Self-attention) | P3 |
| B1 | Channel + Spatial | P1 |
| B2 | Channel + Spatial | P2 |
| B4 | Channel + Spatial | P4 |
| M1 | Channel + Spatial | P3 + P4 |
| M2 | Channel + Spatial | P2 + P3 + P4 |
| O1 | Spatial → Channel | P3 |
| K3, K5 | Spatial attention with 3×3 and 5×5 kernels | P3 |
| X1 | Squeeze-and-Excitation (SE) | P3 |
| X2 | Efficient Channel Attention (ECA) | P3 |
| X3 | CBAM | P3 |
| X4 | Coordinate Attention | P3 |

---

## Project Structure

```text
Lab-8-9/

│
├── lab-8-9.ipynb
├── requirements.txt
├── README.md
├── plots/
```

---

## Installation

Create a virtual environment (recommended):

```bash
python -m venv .venv
```

Activate it.

**Windows**

```bash
.venv\Scripts\activate
```

**Linux/macOS**

```bash
source .venv/bin/activate
```

Install the required packages:

```bash
pip install -r requirements.txt
```

---

## Execution

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
lab-8-9.ipynb
```

Run all cells sequentially. A GPU is strongly recommended. The notebook was written to run on Kaggle with a GPU accelerator, and all plots are saved in EPS format.

---

## Output

The notebook generates the following outputs.

### Data Analysis

* Dataset class distribution and split sizes

* Sample images from every class

### Model Training

* Training and validation accuracy curves

* Training and validation loss curves

* Convergence analysis

* Model parameter count and attention parameter count

### Model Evaluation

* Test accuracy

* Macro precision

* Macro recall

* Macro F1-score

* Inference time per image

* Confusion matrices

### Attention Analysis

* Feature dimensions before and after each attention module

* Feature maps before and after attention

* Channel attention weights

* Spatial attention maps at different positions and kernel sizes

* Self-attention response maps

### Comparison and Interpretation

* Accuracy and macro F1 bar graphs

* Accuracy vs parameters and macro F1 vs inference time

* Grad-CAM for baseline and attention models

* Qualitative comparison on correct and incorrect predictions

* Comparison of SE, ECA, CBAM and Coordinate Attention

---

## Software Requirements

* Python 3.10 or later

* Jupyter Notebook

* TensorFlow / Keras

* NumPy

* Pandas

* Matplotlib

* Scikit-learn

* Pillow

---

## GitHub Repository

The complete source code and notebook for this experiment are available in the `lab-8-9` folder of the GitHub repository.

```text
https://github.com/Mohula-Prasath/Deep_learning_lab/tree/main/lab-8-9
```

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory

**Institution:** Shiv Nadar University Chennai

**Semester:** V (AY 2026–27)