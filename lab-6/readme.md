# CS3807 – Deep Learning Laboratory

## Experiment 6

**RNN, LSTM and GRU for Sequence Classification, CNN-LSTM/GRU Video Classification, and Sequence-to-Sequence Learning**

### Objective

Study recurrent neural network architectures for sequential data and compare SimpleRNN, LSTM and GRU models under the same experimental settings. The experiment covers recurrent sequence classification, training and validation analysis, sequence length analysis, CNN-based spatial feature extraction for video classification, recurrent temporal modelling, and sequence-to-sequence learning.

---

## Additional Analysis

The experiment compares model performance across several studies:

* SimpleRNN, LSTM and GRU architectures

* Training and validation loss comparison

* Training and validation accuracy comparison

* Test-set performance using accuracy, macro precision, macro recall and macro F1-score

* Model parameter count and training time

* Confusion matrix analysis

* Effect of sequence length on classification performance

* CNN-based feature extraction for video classification

* Recurrent modelling of temporal video features

* Sequence-to-sequence learning

The analysis includes:

* Training and validation loss curves

* Training and validation accuracy curves

* Confusion matrices for recurrent models

* Performance comparison of RNN, LSTM and GRU

* Sequence-length performance comparison

* Representative video frames

* Video training and validation curves

* Video classification confusion matrix

* Token accuracy and sequence accuracy for sequence-to-sequence learning

---

## Dataset

### Main Experiment

The notebook uses sequential data for multi-class classification.

* **Number of Classes:** 6

* **Input:** Sequential feature data

* **Sequence Length:** 64 in the main experiment

* **Train/Validation/Test:** Training, validation and test splits are used

For the video experiment, video frames are processed individually using MobileNetV2 and the extracted frame-level features are arranged as temporal sequences.

---

## Model Architecture

### RNN / LSTM / GRU Classification Model

The recurrent classification models consist of:

```text
Input Sequence
        ↓
SimpleRNN / LSTM / GRU
        ↓
Dropout (0.2)
        ↓
Dense (16 neurons, ReLU)
        ↓
Dense (6 neurons, Softmax)
```

### Training Configuration

* **Recurrent Units:** 32

* **Optimizer:** Adam

* **Learning Rate:** 0.001

* **Loss Function:** Sparse Categorical Crossentropy

* **Batch Size:** 32

* **Epochs:** 30

* **Dropout Rate:** 0.2

* **Hidden Dense Layer:** 16 neurons

* **Output Classes:** 6

* **Output Activation:** Softmax

The same experimental settings were used for RNN, LSTM and GRU to provide a controlled comparison.

---

## Video Classification Architecture

The video classification experiment combines a CNN feature extractor with a recurrent network.

```text
Video Frames
        ↓
Individual Video Frames
        ↓
MobileNetV2 CNN
        ↓
Spatial Feature Vectors
        ↓
Temporal Feature Sequence
        ↓
Recurrent Network
        ↓
Video Classification
```

### CNN Feature Extraction

MobileNetV2 is used to extract spatial features from individual video frames. The extracted features are then arranged according to their temporal order.

### Recurrent Temporal Modelling

The recurrent network processes the sequence of CNN-generated features to learn temporal information across consecutive video frames.

---

## Sequence-to-Sequence Learning

The notebook also contains a sequence-to-sequence experiment for studying sequence prediction.

The performance is evaluated using:

* **Token Accuracy:** 0.7172

* **Sequence Accuracy:** 0.1640

Token accuracy evaluates individual token predictions, while sequence accuracy requires the complete sequence to be predicted correctly.

---

## Project Structure

```text
Lab-6/

│
├── lab-6.ipynb
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
lab-6.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Sequential Data Analysis

* Sequential input data analysis

* Sensor signal visualization

* Temporal sequence representation

### RNN / LSTM / GRU Training

* Training and validation loss curves

* Training and validation accuracy curves

* Model training time

* Model parameter count

### Model Evaluation

* Test accuracy

* Macro precision

* Macro recall

* Macro F1-score

* Confusion matrices

### Sequence Length Analysis

* Performance comparison for different sequence lengths

* F1-score comparison across sequence lengths

### Video Classification

* Representative video frames

* CNN-extracted spatial features

* Recurrent temporal modelling

* Training and validation curves

* Video classification confusion matrix

### Sequence-to-Sequence Learning

* Token accuracy

* Sequence accuracy

* Sample test sequences and model predictions

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

* OpenCV

---

## GitHub Repository

The complete source code and notebook for this experiment are available in the `lab-6` folder of the GitHub repository.

```text
https://github.com/Mohula-Prasath/Deep_learning_lab/tree/main/lab-6
```

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory

**Institution:** Shiv Nadar University Chennai

**Semester:** V (AY 2026–27)