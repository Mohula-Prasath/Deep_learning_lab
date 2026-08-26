# CS3807 – Deep Learning Laboratory

## Experiment 5

**Effect of Weight Initialization, Regularization and Optimization Techniques on CNN Performance, with Transfer Learning and Fine-Tuning on MobileNetV2**

### Objective

Study how weight initialization, regularization, batch normalization and optimization algorithms affect CNN training, and implement transfer learning using a pretrained MobileNetV2 model on the Oxford-IIIT Pet dataset. The experiment covers freezing a pretrained convolutional base, training a new classification head, fine tuning selected layers, hyperparameter tuning, 5-fold cross-validation based model selection, and final model evaluation.

---

## Additional Analysis

The experiment compares model performance across several controlled studies:

* Weight initialization (Zero, Random, Xavier, He)
* Regularization (No Regularization, L2, Dropout, Batch Normalization)
* With vs. without Batch Normalization
* Optimizers (SGD, Momentum, RMSProp, Adam)
* Hyperparameter tuning (learning rate, batch size, dropout rate)
* Feature extraction (frozen MobileNetV2 base) vs. fine tuning (last 30 layers unfrozen)
* 5-fold cross-validation across four hyperparameter configurations
* Final model retraining and test-set evaluation

The analysis includes:

* Training and validation accuracy comparison across all studies
* Training and validation loss comparison across all studies
* Cross-validation mean accuracy and standard deviation per configuration
* Test accuracy, precision, recall and F1-score
* Confusion matrix

---

## Dataset

### Main Experiment

* **Dataset:** Oxford-IIIT Pet
* **Training Images:** 5,144
* **Validation Images:** 1,102
* **Testing Images:** 1,103
* **Classes:** 37 (cat and dog breeds)
* **Image Size:** 224 × 224
* **Image Channels:** 3 (RGB)

---

## Model Architecture

The transfer learning model consists of:

```text
Input Image (224 × 224 × 3)
        ↓
MobileNetV2 Convolutional Base (ImageNet Pretrained, Frozen)
        ↓
Global Average Pooling
        ↓
(Optional) Batch Normalization
        ↓
Dense (128 neurons, ReLU, configurable initializer/regularizer)
        ↓
(Optional) Dropout
        ↓
Dense (37 neurons, Softmax)
```

### Fine Tuning Configuration

* Last 30 layers of MobileNetV2 unfrozen after initial training
* All other convolutional layers kept frozen

### Training Configuration

* **Optimizer:** Adam (also compared against SGD, Momentum, RMSProp)
* **Initial Learning Rate:** 0.001 (feature extraction)
* **Fine Tuning Learning Rate:** 0.0001
* **Loss Function:** Sparse Categorical Crossentropy
* **Batch Size:** 32 (also compared: 16, 64)
* **Epochs:** 5 (feature extraction) + 5 (fine tuning); 3 per fold during cross-validation
* **Activation Function:** ReLU
* **Output Activation:** Softmax
* **Cross-Validation:** 5-Fold (`sklearn.model_selection.KFold`) over 4 hyperparameter configurations

---

## Project Structure

```text
Lab-5/
│
├── lab5.ipynb
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
lab5.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Dataset Analysis

* Oxford-IIIT Pet sample images
* Image shape and dataset information
* Training, validation and testing dataset dimensions

### Weight Initialization Study

* Training loss vs. epoch for Zero, Random, Xavier and He initialization
* Validation accuracy vs. epoch for Zero, Random, Xavier and He initialization

### Regularization Study

* Training and validation accuracy comparison (No Regularization, L2, Dropout, Batch Normalization)
* Training and validation loss comparison across regularization strategies
* With vs. without Batch Normalization validation accuracy

### Optimizer Study

* Training loss vs. epoch for SGD, Momentum, RMSProp and Adam
* Validation accuracy vs. epoch for SGD, Momentum, RMSProp and Adam

### Hyperparameter Tuning

* Learning rate vs. validation accuracy
* Batch size vs. validation accuracy
* Dropout rate vs. validation accuracy

### Transfer Learning Setup

* MobileNetV2 base model summary (ImageNet pretrained)
* Total, trainable and non-trainable parameter counts

### Fine Tuning Analysis

* Last-30-layer unfreezing
* Best validation accuracy before vs. after fine tuning
* Training and validation loss across feature extraction and fine tuning

### Cross-Validation and Final Evaluation

* 5-fold cross-validation accuracy per configuration (mean ± standard deviation)
* Final model retraining on the full training set
* Test Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

---

## Software Requirements

* Python 3.10 or later
* Jupyter Notebook
* TensorFlow
* TensorFlow Datasets
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