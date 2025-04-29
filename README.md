# mean_var_std.py

# Mean-Variance-Standard Deviation Calculator

This project is part of the **freeCodeCamp Data Analysis with Python Certification**. It demonstrates the use of NumPy to perform basic statistical calculations (mean, variance, standard deviation, min, max, and sum) on a 3x3 matrix.

## 📊 Project Objective

Given a list of 9 numerical values, the program:
- Converts it into a 3x3 NumPy array
- Calculates the **mean**, **variance**, **standard deviation**, **min**, **max**, and **sum**
- Returns results for:
  - Each column
  - Each row
  - The entire matrix

## 🧰 Technologies Used

- Python 🐍
- NumPy 📐

## ⚙️ How It Works

```python
import numpy as np

def calculate(list):
    if len(list) != 9:
        raise ValueError("List must contain nine numbers.")

    arr = np.array(list).reshape(3, 3)

    calculations = {
        'mean': [np.mean(arr, axis=0).tolist(), np.mean(arr, axis=1).tolist(), np.mean(arr).item()],
        'variance': [np.var(arr, axis=0).tolist(), np.var(arr, axis=1).tolist(), np.var(arr).item()],
        'standard deviation': [np.std(arr, axis=0).tolist(), np.std(arr, axis=1).tolist(), np.std(arr).item()],
        'max': [np.max(arr, axis=0).tolist(), np.max(arr, axis=1).tolist(), np.max(arr).item()],
        'min': [np.min(arr, axis=0).tolist(), np.min(arr, axis=1).tolist(), np.min(arr).item()],
        'sum': [np.sum(arr, axis=0).tolist(), np.sum(arr, axis=1).tolist(), np.sum(arr).item()]
    }

    return calculations


 input = calculate([0, 1, 2, 3, 4, 5, 6, 7, 8])

{
  'mean': [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0],
  'variance': [[6.0, 6.0, 6.0], [0.666..., 0.666..., 0.666...], 6.666...],
  'standard deviation': [[2.449..., 2.449..., 2.449...], [0.816..., 0.816..., 0.816...], 2.581...],
  'max': [[6, 7, 8], [2, 5, 8], 8],
  'min': [[0, 1, 2], [0, 3, 6], 0],
  'sum': [[9, 12, 15], [3, 12, 21], 36]
}

