# CS3807 – Deep Learning Laboratory

## Experiment 1
**Implementation of a Single Layer Perceptron for Binary Classification**

### Objective
Implement a Single Layer Perceptron from scratch for binary classification using Banknote Authentication Dataset and analyze the performance using classification performance metrics.

---

## Dataset
- **Dataset:** Banknote Authentication Dataset
- **Source:** UCI Machine Learning Repository
- **Instances:** 1372
- **Features:** 4 Numerical Features
- **Classes:** 2


---

## Project Structure

```
Lab-1/
│
├── lab1.ipynb
├── data_banknote_authentication.txt
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

```
lab1.ipynb
```

Run all cells sequentially.

---

## Output

The output of the notebook includes:

- Plots of Exploratory Data Analysis (EDA)
- Training error v/s Epochs
- Comparison of different learning rates
- Plot of weights evolution
- Plot of bias evolution
- Confusion matrix
- Performance metrics (Accuracy, Precision, Recall, F1 Score)

---

## Software Requirements

- Python 3.10 or later
- Jupyter Notebook

---

## Course Information

**Course:** CS3807 – Deep Learning Laboratory  
**Institution:** Shiv Nadar University Chennai  
**Semester:** V (AY 2026–27)
