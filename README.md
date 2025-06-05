# 🚗 Toyota Corolla Price Prediction

A comprehensive machine learning project that predicts used car prices based on vehicle specifications and characteristics using various regression algorithms.

![Car Price Prediction](https://img.shields.io/badge/Toyota_Corolla-Regression-darkred) 
![Python 3.6+](https://img.shields.io/badge/Python-3.6+-blue)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Latest-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📋 Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset Information](#dataset-information)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Algorithms Implemented](#algorithms-implemented)
6. [Performance Evaluation](#performance-evaluation)
7. [Results](#results)
8. [Conclusion](#conclusion)
9. [License](#license)  

## 📊 Project Overview

This project investigates how different vehicle attributes of Toyota Corolla cars affect their market pricing. By analyzing characteristics like age, mileage, engine specifications, and various features, the project builds regression models to predict the market value of used Toyota Corolla vehicles based on their specifications and condition.

The analysis includes comprehensive data visualization, preprocessing, and the implementation of seven different regression algorithms with detailed performance comparisons using RMSE, R², and cross-validation metrics.

## 🚙 Dataset Information

The dataset contains information about 1,436 Toyota Corolla vehicles with their market prices and specifications.

### Features

The dataset contains the following vehicle attributes:

1. **Age** (months) – Age of the vehicle from manufacture date
2. **KM** (kilometers) – Total distance traveled, indicating usage and wear
3. **FuelType** – Type of fuel system (Petrol, Diesel, CNG)
4. **HP** (horsepower) – Engine power output affecting performance
5. **MetColor** – Binary indicator of metallic paint finish
6. **Automatic** – Binary indicator of transmission type (automatic vs manual)
7. **CC** (cubic centimeters) – Engine displacement volume
8. **Doors** – Number of doors on the vehicle (2, 3, 4, or 5)
9. **Weight** (kg) – Vehicle weight affecting fuel efficiency and performance

### Target Variable

- **Price**: Continuous variable representing the market value of the Toyota Corolla in euros

## 🔧 Installation

To set up this project locally, follow these steps:

```bash
# Clone this repository
git clone https://github.com/yourusername/toyota-corolla-price-prediction.git
cd toyota-corolla-price-prediction

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate

# Install required packages
pip install -r requirements.txt
```

### Dependencies

The project requires the following Python libraries:
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- math
- collections

## 🚀 Usage

You can run the project by executing the Jupyter notebook:

```bash
jupyter notebook Toyota_Corolla_Price_Prediction.ipynb
```

## 🧮 Algorithms Implemented

This project implements and compares seven regression algorithms:

1. **Linear Regression**
   - Establishes a linear relationship between vehicle features and price
   - Uses least squares method to find the best-fitting line through data points

2. **Polynomial Regression (2nd Degree)**
   - Extends linear regression by creating polynomial features to capture non-linear relationships
   - Creates interaction terms and squared terms from original features

3. **Ridge Regression**
   - Regularized version of linear regression using L2 penalty
   - Addresses overfitting and multicollinearity by shrinking coefficients

4. **Lasso Regression**
   - Uses L1 regularization for both regularization and automatic feature selection
   - Can shrink some coefficients to zero, effectively removing irrelevant features

5. **Support Vector Regression (SVR)**
   - Extends Support Vector Machine concept to regression problems
   - Uses epsilon margin and kernel functions to handle non-linear relationships

6. **Decision Tree Regression**
   - Creates a tree-like model where each leaf contains a predicted price value
   - Highly interpretable but prone to overfitting

7. **Random Forest Regression**
   - Ensemble method combining multiple decision trees
   - Final prediction is the average of all individual tree predictions
   - Uses bootstrap aggregating to improve performance and reduce overfitting

## 📏 Performance Evaluation

The models are evaluated using comprehensive regression metrics:

- **Root Mean Squared Error (RMSE)** - Standard deviation of prediction errors in original price units

![RMSE Comparison](https://iili.io/FdvLBWu.png)

- **R² Score (Training & Test)** - Proportion of variance explained by the model

![R² Score Comparison](https://iili.io/FdvQ4vp.png)

- **Cross-Validation Score** - Average R² performance across multiple validation folds

![Cross-Validation Score](https://iili.io/FdvtVeV.png)


## 📈 Results

**The Random Forest Regression** achieved the best overall performance:

- **RMSE**: 1,092.35 euros (lowest prediction error)
- **Test R²**: 0.9159 (explains 91.59% of price variance)
- **Cross-Validation Score**: 0.8956 (most stable performance)
- **Training R²**: 0.9862 (excellent fit without severe overfitting)

![Algorithm Comparison](https://iili.io/FdvDeZ7.png)

*Other notable performers:*
- **Lasso Regression** achieved second-best performance (RMSE: 1,177.51) with automatic feature selection
- **Linear Regression** and **Ridge Regression** provided consistent baseline performance
- **Decision Tree** and **Polynomial Regression** showed significant overfitting issues

### Performance Summary Table

| Algorithm | RMSE | R² (Test) | Cross-Validation | Overfitting Risk |
|-----------|------|-----------|------------------|------------------|
| **Random Forest** | **1,092.35** | **0.9159** | **0.8956** | Low |
| **Lasso Regression** | **1,177.51** | **0.9023** | 0.7428 | Low |
| **Ridge Regression** | 1,359.39 | 0.8698 | 0.7785 | Low |
| **Linear Regression** | 1,398.46 | 0.8622 | 0.8481 | Minimal |
| **Support Vector Regression** | 1,525.53 | 0.8360 | **0.8718** | Low |
| **Decision Tree** | 1,485.50 | 0.8445 | 0.8193 | **High** |
| **Polynomial (2nd)** | 1,837.85 | 0.7620 | 0.8481 | **High** |

## 🏆 Conclusion

The analysis revealed that **Random Forest Regression** is the optimal choice for Toyota Corolla price prediction, demonstrating superior accuracy and robust generalization capability. The model effectively captures the complex relationships between vehicle specifications and market pricing.

Key findings:
- Random Forest outperformed all other algorithms with the lowest RMSE and highest R² score
- The model provides reliable price predictions with typical errors around ±1,092 euros
- Features like age, mileage, and engine specifications were particularly important in price determination
- Ensemble methods significantly outperformed individual algorithms in both accuracy and stability

### Business Impact
This model can be effectively used by:
- **Car dealers** for accurate inventory pricing
- **Individual sellers** for competitive price setting
- **Buyers** for fair value assessment
- **Insurance companies** for vehicle valuation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---