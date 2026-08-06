# CS3807 – Deep Learning Laboratory

## Experiment 3

**Implementation of a Convolutional Neural Network (CNN) for Multi-Class Image Classification**

### Objective

Design and implement a Convolutional Neural Network (CNN) using TensorFlow/Keras for multi-class image classification on the CIFAR-10 dataset and analyze the learning behavior and performance of the model.

The experiment also includes visualization of intermediate feature maps to understand how convolutional layers progressively extract visual features from images.

---

## Additional Analysis

The experiment compares different pooling strategies to study their effect on CNN performance:

* Max Pooling
* Average Pooling

The comparison is performed using the same CNN architecture, with only the pooling operation changed.

The analysis includes:

* Test accuracy comparison
* Test loss comparison
* Precision, recall and F1-score
* Classification report
* Confusion matrix
* Validation performance comparison

---

## Dataset

### Main Experiment

* **Dataset:** CIFAR-10
* **Training Images:** 50,000
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

The CNN consists of:

```text
Input Image (32 × 32 × 3)
        ↓
Conv2D (32 filters, 3 × 3 kernel)
        ↓
Max/Average Pooling (2 × 2)
        ↓
Conv2D (64 filters, 3 × 3 kernel)
        ↓
Max/Average Pooling (2 × 2)
        ↓
Flatten
        ↓
Dense (128 neurons)
        ↓
Dropout (0.5)
        ↓
Dense (10 neurons, Softmax)
```

### Training Configuration

* **Optimizer:** Adam
* **Learning Rate:** 0.001
* **Loss Function:** Sparse Categorical Crossentropy
* **Batch Size:** 64
* **Epochs:** 20
* **Activation Function:** ReLU
* **Output Activation:** Softmax
* **Validation Split:** 20%

---

## Project Structure

```text
Lab-3/
│
├── lab3.ipynb
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
lab3.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Dataset Analysis

* CIFAR-10 sample images
* Class distribution plot
* Image shape and dataset information
* Pixel value analysis

### CNN Training and Evaluation

* CNN model summary
* Training Loss vs Epoch
* Validation Loss vs Epoch
* Training Accuracy vs Epoch
* Validation Accuracy vs Epoch
* Test Loss
* Test Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Classification Report

### Feature Map Analysis

* Original input image
* Intermediate feature maps from the first convolutional layer
* Intermediate feature maps from the second convolutional layer
* Feature map shape analysis

### Pooling Strategy Comparison

* Max Pooling model
* Average Pooling model
* Max Pooling vs Average Pooling test accuracy
* Max Pooling vs Average Pooling test loss
* Validation accuracy comparison
* Validation loss comparison
* Average Pooling confusion matrix
* Average Pooling classification report

### Parameter Analysis

The trainable parameters of the convolutional layers are analyzed based on the CNN architecture and model summary.

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
