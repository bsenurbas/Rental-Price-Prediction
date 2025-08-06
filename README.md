# Real Estate Rent Modeling Tool – Technical Design Document

## Overview

This tool enables rent prediction and classification using real estate datasets. It is designed to process data from a static file, apply statistical analysis, and train predictive models for both classification and regression tasks. The tool also allows users to input new data for prediction, with outputs delivered through visualizations and summaries.

---

## System Structure

### Modules

- **Data Preprocessing Module**  
  Handles cleaning, transformation, and standardization of raw real estate data.

- **Statistical Analysis Module**  
  Provides visual and numerical exploration of data, including correlation analysis and outlier detection.

- **Classification Module**  
  Categorizes rent values using a classification model, generating performance metrics.

- **Regression Module**  
  Predicts continuous rent values and evaluates performance using standard and custom R² metrics with tolerance.

### Data Source

- Input is read from a static structured dataset (e.g., CSV file).
- No external API or dynamic upload interface is used.

---

## Functionality

### 1. Preprocessing

- Converts data types for numerical and categorical fields.
- Removes missing values and outliers.
- Outputs a clean dataset ready for modeling.

### 2. Statistical Exploration

- Computes descriptive statistics.
- Generates correlation matrices.
- Uses histograms and boxplots for distribution visualization.
- Applies IQR-based filtering to detect and remove outliers.

### 3. Classification Workflow

- Categorizes rent values using interval binning.
- Prepares data pipelines for scaling and encoding.
- Trains a classification model and evaluates accuracy on train/test split.

### 4. Regression Workflow

- Models continuous rent predictions using linear regression.
- Uses pipelines for consistent preprocessing.
- Evaluates with:
  - Standard R²
  - Absolute tolerance-based R²
  - Percentage-based tolerance R²

---

## Prediction Interface

- The user manually inputs feature values via code cells.
- The system outputs prediction results.
- Visualizations and summary tables are used to communicate results.

---

## Output Presentation

- Key performance metrics are printed to the console.
- Prediction results and errors are displayed via graphs and tabular summaries.
- Custom tolerance-based metrics provide practical insights into model accuracy.

---

## Dependencies

- Requires interpreter version 3.9 or higher.
- Uses the following libraries:
  - Data Processing: pandas, numpy
  - Visualization: matplotlib, seaborn
  - Machine Learning: scikit-learn

---

## Usage Summary

| Stage             | Objective                                       |
|-------------------|-------------------------------------------------|
| Data Preprocessing| Clean and standardize raw housing data         |
| Statistical Review| Analyze distributions and correlations         |
| Classification    | Categorize rental price ranges                 |
| Regression        | Predict exact rental prices with error margins |

---

## Evaluation Highlights

| Metric                             | Value    |
|-----------------------------------|----------|
| Standard R²                       | ~0.50    |
| R² with ±10,000 TL tolerance      | ~0.66    |
| R² with ±50% tolerance (relative) | ~0.79    |

---

## Reference Resource

The methodology aligns with a public video tutorial series:  
**"Machine Learning with Real Data: Rent Prediction" – YouTube Playlist**  
[Watch the Series](https://www.youtube.com/playlist?list=PL30NBs02RsiVtALCWtMyRT45caVKXhpdU)

---

