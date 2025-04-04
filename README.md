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

### 🔹 Linear Regression (after outlier removal)
- **R² Score**: 0.9657  
- **Residual Standard Error (RSE)**: 18.46

### 🔹 Random Forest Regressor
- **R² Score (test)**: 0.9977  
- **Accuracy**: 96.75%  
- **Mean Absolute Error (MAE)**: 1.95  
- **% Variance Explained**: 98.8  
- **Mean Squared Residuals**: 152.93

Random Forest significantly outperformed Linear Regression in capturing non-linear interactions and delivering more accurate predictions, with nearly perfect R² and low error metrics.

## 🔍 Key Findings
- GPU memory bandwidth is significantly influenced by **memory bus width**, **memory speed**, and **texture rate**, as revealed by both regression coefficients and statistical tests.
- **Shapiro-Wilk** and **Levene’s tests** confirmed the need for non-parametric analysis, followed by **Dunn’s test** to identify group-wise differences.
- Linear Regression achieved strong performance after outlier removal (R² = 0.9657), but struggled with non-linear patterns.
- Random Forest Regressor provided the best predictive accuracy (R² = 0.9977), with low error (MAE = 1.95) and high explanatory power (98.8% variance explained).
- Ensemble methods like Random Forest proved more robust and accurate than linear models for this multi-feature prediction task.

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


