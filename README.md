# 📊 GPU Bandwidth Prediction

This project was developed as part of the *Probability and Statistics* course at HCMUT. It explores how statistical techniques and machine learning models can be used to analyze GPU hardware data and predict memory bandwidth.

## 🧠 Objective

To use both **descriptive** and **inferential statistics** to analyze GPU datasets, and to apply **regression models** to predict GPU memory bandwidth from hardware specifications.

## 📁 Dataset

This project uses the [Computer Parts Dataset](https://www.kaggle.com/datasets/iliassekkaf/computerparts?resource=downlo) from Kaggle. It includes 3,406 GPU records with a variety of technical specifications and performance data.

Selected key columns:
- **Architecture**, **Boost_Clock**, **Core_Speed**, **Memory_Type**, **Memory_Speed**
- **DVI_Connection**, **HDMI_Connection**, **DisplayPort_Connection**, **VGA_Connection**
- **Integrated**, **Notebook_GPU**, **SLI_Crossfire**
- **L2_Cache**, **ROP**, **TMUs**, **Shader**, **Texture_Rate**
- **Release_Date**, **Release_Price**, **Power_Connector**, **Max_Power**, **PSU**
- **Open_GL**, **Direct_X**, **Resolution_WxH**, **Best_Resolution**
- **Memory_Bandwidth** (target variable)

> ⚠️ Some columns contain missing values (e.g., `DisplayPort_Connection`, `HDMI_Connection`, `Shader`, `TMUs`) and were handled during preprocessing.

## 🛠️ Methods Used

### 📈 Exploratory Data Analysis (EDA)
- Visualizations by vendor, architecture, and memory type using `seaborn`
- Distribution plots and correlation heatmaps for numeric features

### 🧪 Statistical Testing
- **Normality Check**: Shapiro-Wilk Test  
- **Homogeneity of Variances**: Levene’s Test  
- **Group Mean Comparisons**:
  - Parametric: t-test, ANOVA  
  - Non-parametric: Kruskal-Wallis  
- **Post-hoc Analysis**: Dunn Test for identifying which group pairs differ significantly

### 🤖 Machine Learning Models
- **Linear Regression**
- **Random Forest Regression**

### 📊 Evaluation Metrics
- **R² Score**
- **Mean Squared Error (MSE)**

## ✅ Results

- **Random Forest Regressor** achieved:
  - **R² Score**: 0.82  
  - **MSE**: 6.5
- Random Forest effectively captured non-linear relationships and outperformed Linear Regression.

## 🔍 Key Findings
- GPU memory bandwidth is strongly influenced by memory type, memory speed, and bus width.
- Statistical testing revealed significant differences between GPU groups based on vendor and architecture.
- Random Forest showed robust performance across both training and test sets.

## 💻 Technologies Used

- Python 3.x  
- Pandas, NumPy  
- Seaborn, Matplotlib  
- SciPy (for hypothesis testing)  
- Scikit-learn (for regression models)

## 📎 Files

- `GPU_Analysis.ipynb` – Full analysis and modeling notebook
- `README.md` – Project overview and documentation
- `Report.pdf` – Project report

## 🔗 Resources

- 📄 [Kaggle Dataset – Computer Parts](https://www.kaggle.com/datasets/iliassekkaf/computerparts?resource=downlo)  


