# CS3807 – Deep Learning Laboratory

## Experiment 4

**Comparative Study of Deep Convolutional Neural Network Architectures Using Transfer Learning**

### Objective

Study the evolution of deep CNN architectures (LeNet-5, AlexNet, VGG16, GoogleNet, ResNet) and implement transfer learning using a pretrained VGG16 model on the CIFAR-10 dataset. The experiment covers freezing a pretrained convolutional base, training a new classification head, fine tuning selected convolutional layers, and evaluating classification performance.

---

## Additional Analysis

The experiment compares model performance before and after fine tuning:

* Feature extraction (frozen VGG16 base)
* Fine tuning (unfrozen `block5` convolutional layers)

The comparison is performed using the same VGG16-based architecture, with only the trainable layers and learning rate changed between phases.

The analysis includes:

* Training and validation accuracy comparison (before vs. after fine tuning)
* Training and validation loss comparison (before vs. after fine tuning)
* Test accuracy, precision, recall and F1-score
* Classification report
* Confusion matrix
* Misclassified image analysis
* Trainable vs. non-trainable parameter comparison

---

## Dataset

### Main Experiment

* **Dataset:** CIFAR-10
* **Training Images:** 45,000
* **Validation Images:** 5,000
* **Testing Images:** 10,000
* **Classes:** 10
* **Image Size:** 32 × 32
* **Image Channels:** 3 (RGB)

The ten classes are:

* Airplane
* Automobile
* Bird
* Cat
* Deer
* Dog
* Frog
* Horse
* Ship
* Truck

---

## Model Architecture

The transfer learning model consists of:

```text
Input Image (32 × 32 × 3)
        ↓
VGG16 Convolutional Base (ImageNet Pretrained, Frozen)
        ↓
Global Average Pooling
        ↓
Dense (256 neurons, ReLU)
        ↓
Dense (10 neurons, Softmax)
```

### Fine Tuning Configuration

* `block5` layers of VGG16 unfrozen after initial training
* All other convolutional layers kept frozen

### Training Configuration

* **Optimizer:** Adam
* **Initial Learning Rate:** 0.001 (feature extraction)
* **Fine Tuning Learning Rate:** 0.0001
* **Loss Function:** Categorical Crossentropy
* **Batch Size:** 32
* **Epochs:** 5 (feature extraction) + 5 (fine tuning)
* **Activation Function:** ReLU
* **Output Activation:** Softmax
* **Validation Data:** 5,000 held-out training images

---

## Project Structure

```text
Lab-4/
│
├── lab4.ipynb
├── requirements.txt
├── README.md
├── images/
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
lab4.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Dataset Analysis

* CIFAR-10 sample images
* Image shape and dataset information
* Training, validation and testing dataset dimensions

### Transfer Learning Setup

* VGG16 base model summary (ImageNet pretrained)
* Total, trainable and non-trainable parameter counts (feature extraction phase)

### Model Training and Evaluation

* Training accuracy and loss (feature extraction phase)
* Validation accuracy and loss (feature extraction phase)
* Training Accuracy vs Epoch (combined, with fine tuning marker)
* Validation Accuracy vs Epoch (combined, with fine tuning marker)
* Training Loss vs Epoch (combined, with fine tuning marker)
* Validation Loss vs Epoch (combined, with fine tuning marker)
* Test Loss
* Test Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Classification Report

### Fine Tuning Analysis

* `block5` layer unfreezing
* Trainable and non-trainable parameter counts (post fine tuning)
* Best validation accuracy before vs. after fine tuning
* Fine tuning improvement (percentage points)

### Misclassification Analysis

* Sample misclassified test images
* True label vs. predicted label comparison

### Parameter Analysis

The trainable and non-trainable parameters of the VGG16-based model are analyzed for both the feature extraction phase (frozen base) and the fine tuning phase (`block5` unfrozen).

---

## Software Requirements

* Python 3.10 or later
* Jupyter Notebook
* TensorFlow
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory
**Institution:** Shiv Nadar University Chennai
**Semester:** V (AY 2026–27)