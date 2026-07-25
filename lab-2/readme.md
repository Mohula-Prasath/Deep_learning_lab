# CS3807 – Deep Learning Laboratory

## Experiment 2
**Implementation of a Multi-Layer Perceptron (MLP) for Multi-Class Image Classification**

### Objective
Implement a Multi-Layer Perceptron (MLP) using TensorFlow/Keras for multi-class image classification on the Fashion-MNIST dataset and perform automated hyperparameter optimization using RandomizedSearchCV with the SciKeras wrapper.

---

## Additional Task

Implement the Perceptron Learning Algorithm for the XOR logic gate using Python.

The implementation includes:

- Perceptron learning algorithm from scratch
- Weight updates after every misclassification
- Bias updates
- Decision boundary visualization after every epoch
- Saving decision boundary plots for each epoch
- Analysis of the non-convergence behavior of the perceptron for the XOR gate
- Training for a fixed number of epochs to observe the repeating weight update pattern

---

## Dataset

### Main Experiment

- **Dataset:** Fashion-MNIST
- **Training Images:** 60,000
- **Testing Images:** 10,000
- **Classes:** 10
- **Image Size:** 28 × 28

### Additional Task

The XOR gate uses a manually created truth table instead of an external dataset.

---

## Project Structure

```
Lab-2/
│
├── lab-2.ipynb
├── lab2_1.ipynb
├── requirements.txt
├── README.md
├── dl_lab_2.pdf
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

```
lab2.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Main Experiment

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

### Additional Task

- XOR Gate training
- Weight updates after each misclassification
- Final weights and bias after the last epoch
- Decision boundary plots after every epoch
- Saved decision boundary figures in the `plots_lab_2/` directory
- Analysis showing why a single-layer perceptron fails to converge for the XOR gate due to non-linear separability

---

## Software Requirements

- Python 3.10 or later
- Jupyter Notebook

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory  
**Institution:** Shiv Nadar University Chennai  
**Semester:** V (AY 2026–27)