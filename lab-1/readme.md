# CS3807 – Deep Learning Laboratory

## Experiment 1
**Implementation of a Single Layer Perceptron for Binary Classification**

### Objective
Implement a Single Layer Perceptron from scratch for binary classification using the Banknote Authentication Dataset and analyze the performance using classification performance metrics.

---

## Additional Task

Implement the Perceptron Learning Algorithm for the following logic gates:

- OR Gate
- AND Gate
- NOT Gate

The implementation includes:

- Perceptron learning algorithm from scratch
- Weight updates after every misclassification
- Bias updates
- Decision boundary visualization after every epoch
- Saving decision boundary plots for each epoch
- Training until convergence or the maximum number of epochs

---

## Dataset

### Main Experiment
- **Dataset:** Banknote Authentication Dataset
- **Source:** UCI Machine Learning Repository
- **Instances:** 1372
- **Features:** 4 Numerical Features
- **Classes:** 2

### Additional Task
The OR, AND and NOT gates use manually created truth tables instead of an external dataset.

---

## Project Structure

```
Lab-1/
│
├── lab1.ipynb
├── lab1_2.ipynb
├── data_banknote_authentication.txt
├── requirements.txt
├── README.md
├── dl_lab_1.pdf
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
lab1.ipynb
```

Run all cells sequentially.

---

## Output

The notebook generates the following outputs.

### Main Experiment

- Exploratory Data Analysis (EDA) plots
- Training Error vs Epochs
- Learning Rate Comparison
- Weight Evolution plots
- Bias Evolution plots
- Confusion Matrix
- Performance Metrics (Accuracy, Precision, Recall and F1-score)

### Additional Task

- OR Gate training
- AND Gate training
- NOT Gate training
- Weight updates after each misclassification
- Final learned weights and bias
- Decision boundary plots after every epoch
- Saved decision boundary figures in the `plots/` directory

---

## Software Requirements

- Python 3.10 or later
- Jupyter Notebook

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory  
**Institution:** Shiv Nadar University Chennai  
**Semester:** V (AY 2026–27)