# 🌸 Iris Dataset Exploration and Visualization

## 📌 Objective
This project demonstrates how to load, inspect, and visualize the famous Iris dataset to understand feature relationships, data distribution, and potential outliers.

---

## 🧰 Tools Used
- Python
- pandas
- seaborn
- matplotlib

---

## 📂 Dataset
- **Source:** Built-in dataset from the `seaborn` library.
- **Features:**
  - `sepal_length`
  - `sepal_width`
  - `petal_length`
  - `petal_width`
  - `species` (target class)

---

## ✅ Steps Performed

### 1. Load the Dataset
- Used `seaborn.load_dataset('iris')` to import the dataset as a pandas DataFrame.

### 2. Inspect the Dataset
- Printed dataset **shape**, **columns**, and **first few rows**.
- Used `.info()` and `.describe()` to view data types and summary statistics.

### 3. Visualizations
- 📊 **Scatter Plot Matrix** using `seaborn.pairplot()` to show relationships between features grouped by species.
- 📈 **Histograms** using `pandas.DataFrame.hist()` to show distribution of numeric values.
- 📦 **Box Plots** using `seaborn.boxplot()` to detect outliers in each feature grouped by species.

---

## 📸 Example Visuals

< Add screenshots or image links of your visualizations here >

---

## 🚀 How to Run
1. Make sure you have Python installed.
2. Install required libraries:
   ```bash
   pip install pandas seaborn matplotlib
