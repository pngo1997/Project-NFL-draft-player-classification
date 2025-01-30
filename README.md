# 🏗️ NFL Draft Prediction Analysis  

## 📜 Overview  
This project analyzes **NFL Draft data (1985-2015)** to explore **player performance patterns, draft trends, and classification of players by conference (AFC/NFC)**. The dataset includes **8,435 observations and 34 variables**, later refined to **4,895 observations and 11 variables** after preprocessing. The objective is to identify **key predictors** for player selection and develop **classification models** using **k-NN, SVM, and Decision Trees**.  

## 🎯 Problem Explanation  
The **NFL Draft** is a selection process where teams recruit college football players based on **performance stats, awards, and career potential**. This project examines:  

1. **Player Performance Factors**  
   - **Pro-Bowler Selections (`pb`)**: Popularity-based selection for top players.  
   - **All-Pro 1st Team (`ap1`)**: Performance-based ranking of top players.  
   - **Career Approximate Value (`carav`)**: A statistical metric estimating a player’s impact.  
   - **Games Played (`g`)**: Number of games played over their career.  

2. **Conference-Based Drafting Patterns**  
   - The dataset was **split into AFC and NFC** teams to analyze differences in draft strategies.  
   - Examines **whether a player’s conference influences draft probability**.  

3. **Classification Models for Player Drafting**  
   - **k-NN & SVM** were used to predict **AFC vs. NFC classification** based on player stats.  
   - **Decision Trees & PCA** were applied to visualize classification accuracy.  

## 🛠️ Implementation Details  
### **Data Cleaning & Preprocessing**  
- **Missing Data Handling**:  
  - Removed features with excessive missing values (`pass_yds`, `rush_att`, `rec_tds`, etc.).  
  - Excluded players drafted **before 1994** due to incomplete **college records**.  

- **Feature Engineering & Normalization**:  
  - **Min-Max Scaling** for Pro-Bowler (`pb`), All-Pro (`ap1`), and Starter Seasons (`st`).  
  - **Z-Score Normalization** for Career Approximate Value (`carav`).  
  - **Binning Age (`age`)**: Players were grouped as **"≤23 years" or "23+ years"** to reflect draft eligibility.  

### **Exploratory Data Analysis (EDA)**  
- **Density Plots**: Show correlation between **All-Pro selections and Pro-Bowlers**.  
- **Scatter Plots**: Analyzed **draft pick position vs. career value**.  
- **Histograms**: Examined distribution of **age and starting players (`st`)**.  
- **Bar Graphs**: Compared positional drafting patterns in **AFC vs. NFC teams**.  

### **Clustering & Classification Models**  
- **Clustering (HAC & k-Means)**  
  - Hierarchical Agglomerative Clustering (**HAC**) suggested **k=2 clusters**.  
  - k-Means was preferred due to **better interpretability** (final `k=2`).  

- **Classification Models**  
  - **Support Vector Machines (SVM)**: Tuned **C=1.9**, but resulted in ~50% accuracy.  
  - **k-Nearest Neighbors (k-NN)**: Tuned `k=27`, achieving ~50% accuracy.  
  - **Decision Tree Classification**: Achieved **precision = 82.3%, recall = 49.5%**.  

### **Model Evaluation**  
- **Confusion Matrix** for classification performance.  
- **ROC Curve & AUC Analysis** (AUC = 0.5, indicating no clear predictive pattern).  

## 🚀 Technologies Used  
- **R** (for data preprocessing, visualization, and modeling).  
- **tidyverse, ggplot2** (for data manipulation and EDA).  
- **caret, rpart, factoextra** (for classification models & clustering).  
