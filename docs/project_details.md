# Project Details: Student Exam Score Prediction

## Introduction
This project predicts student exam scores based on hours studied using Linear and Polynomial Regression models. The goal is to compare their performance to determine which model better captures the relationship between study hours and exam scores, using metrics like R² Score, Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE).

## Dataset
- **File**: `StudentPerformanceFactors.csv`
- **Feature**: `Hours_Studied` (independent variable)
- **Target**: `Exam_Score` (dependent variable)
- **Description**: The dataset contains student performance data, with hours studied as the predictor and exam scores as the outcome. The variance of `Exam_Score` indicates the spread of scores, with ~23% explained by hours studied in both models.

## Models
### Linear Regression
- **Description**: Models a linear relationship: \( \text{Exam_Score} = \beta_0 + \beta_1 \cdot \text{Hours_Studied} \).
- **Parameters**: 2 (intercept, slope).
- **Purpose**: Assumes a straight-line relationship between study hours and scores.

### Polynomial Regression (Degree 2)
- **Description**: Models a quadratic relationship: \( \text{Exam_Score} = \beta_0 + \beta_1 \cdot \text{Hours_Studied} + \beta_2 \cdot \text{Hours_Studied}^2 \).
- **Parameters**: 3 (intercept, linear term, quadratic term).
- **Purpose**: Captures potential non-linear patterns in the data.

## Evaluation Metrics
- **R² Score**: Proportion of variance in exam scores explained by the model (0 to 1, higher is better).
- **MAE**: Average absolute difference between predicted and actual scores (in points, lower is better).
- **RMSE**: Square root of average squared differences, emphasizing larger errors (in points, lower is better).

### Test Set Performance
- **Data Split**: 80% training, 20% test (random_state=42).
- **Linear Regression**:
  - R² Score: 0.2320
  - MAE: 2.4476 points
  - RMSE: 3.2948 points
- **Polynomial Regression (Degree 2)**:
  - R² Score: 0.2328
  - MAE: 2.4448 points
  - RMSE: 3.2932 points

## Variance Analysis
- **Dataset Variance**: The variance of `Exam_Score` reflects the spread of scores. Both models explain ~23% of this variance (R² ≈ 0.23), leaving ~77% unexplained, suggesting hours studied is a weak predictor.
- **Explained Variance**: Polynomial Regression’s slightly higher R² (0.2328 vs. 0.2320) indicates it captures marginally more variance, but the difference is minimal.
- **Unexplained Variance**: RMSE² approximates residual variance (~10.85 for both models), indicating similar unexplained variance.

## Results
- **Performance**: Both models perform nearly identically, with Polynomial Regression showing a slight edge (R²: 0.2328 vs. 0.2320, MAE: 2.44 vs. 2.45, RMSE: 3.29 vs. 3.29). This suggests the relationship is weak or nearly linear, with the quadratic term adding little value.
- **Model Choice**: Linear Regression is recommended for its simplicity (2 parameters vs. 3) unless further analysis reveals non-linear patterns.

## Implementation Details
- **Libraries**: `pandas`, `numpy`, `scikit-learn`, `matplotlib`.
- **Key Steps**:
  1. Load and preprocess the dataset.
  2. Split data (80% train, 20% test).
  3. Train Linear and Polynomial Regression models.
  4. Compute R², MAE, and RMSE.
  5. Visualize model fits.

## Recommendations
- **Add Features**: Include predictors like sleep hours or study habits to explain more variance.
- **Explore Models**: Test other algorithms (e.g., decision trees) with additional features.
- **Cross-Validation**: Use k-fold cross-validation for robust performance evaluation.

## Usage
1. Place `StudentPerformanceFactors.csv` in the working directory.
2. Install dependencies: `pip install pandas numpy scikit-learn matplotlib`.
3. Run the main script to train models and view results.

## Notes
- Update the dataset path if necessary.
- Date: August 21, 2025.