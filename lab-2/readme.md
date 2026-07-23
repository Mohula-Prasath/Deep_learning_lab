# CS3807 – Deep Learning Laboratory

## Experiment 2
**Implementation of a Multi-Layer Perceptron (MLP) for Multi-Class Image Classification**

### Objective
Implement a Multi-Layer Perceptron (MLP) using TensorFlow/Keras for multi-class image classification on the Fashion-MNIST dataset and perform automated hyperparameter optimization using RandomizedSearchCV with the SciKeras wrapper.

---

## Dataset

- **Dataset:** Fashion-MNIST
- **Training Images:** 60,000
- **Testing Images:** 10,000
- **Classes:** 10
- **Image Size:** 28 × 28

---

## Project Structure

```
Lab-2/
│
├── lab2.ipynb
├── requirements.txt
├── README.md
├── plots_lab_2/
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

```
lab2.ipynb
```

Run all cells sequentially.

---

## Output

The output of the notebook includes:

- Sample Fashion-MNIST images
- Class distribution plot
- Training Accuracy vs Epoch
- Validation Accuracy vs Epoch
- Training Loss vs Epoch
- Validation Loss vs Epoch
- Confusion Matrix
- Hyperparameter Search Results
- Best Model Accuracy Comparison
- Performance metrics (Accuracy, Precision, Recall, F1 Score)
- Classification Report

---

## Software Requirements

- Python 3.10 or later
- Jupyter Notebook

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory  
**Institution:** Shiv Nadar University Chennai  
**Semester:** V (AY 2026–27)