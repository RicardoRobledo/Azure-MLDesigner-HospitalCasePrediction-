# Hospital Case Prediction with Azure ML Designer

Regression model built with Azure ML Designer to predict monthly hospital case counts based on diagnosis, year, and month.

## 📊 Dataset

**Source:** [Hospital Records for Data Cleaning (Medium)](https://www.kaggle.com/datasets/nudratabbas/hospital-records-for-data-cleaning-medium)

Synthetic hospital records dataset with clinical terminology that includes logical inconsistencies and missing values typical of medical data systems.

## 🎯 Objective

Predict monthly hospital case counts (`Cases`) using medical diagnosis (`Diagnosis`), year (`Year`), and month (`Month`) as predictor variables.

## 🔧 Technologies Used

- **Azure Machine Learning Studio** - Cloud ML platform
- **Azure ML Designer** - Visual no-code tool for pipelines
- **Python 3.x** - Custom scripting for feature engineering
- **Pandas** - Data manipulation and transformation
- **Scikit-learn** - Linear regression algorithm

## 🏗️ Methodology

### Data Preprocessing
1. **Column selection**: `AdmissionDate` and `Diagnosis`
2. **Missing value imputation**: Mode imputation for `Diagnosis` column
3. **Feature Engineering**: 
   - Convert `AdmissionDate` to datetime format
   - Extract temporal features (`Year`, `Month`)
   - Group by diagnosis and temporal period
   - Count cases as target variable

### Model Training
- **Algorithm**: Linear Regression
- **Data split**: 70% training / 30% testing
- **Split type**: Non-random due to temporal nature of data
- **Target variable**: `Cases` (monthly case count)

## 📈 Results

| Metric | Value |
|---------|-------|
| Mean Absolute Error (MAE) | 2.0259 |
| Root Mean Squared Error (RMSE) | 2.806342 |
| Relative Squared Error | 0.299339 |
| Relative Absolute Error | 0.471088 |
| **Coefficient of Determination (R²)** | **0.700661** |

### Interpretation
The model achieves an **R² of 0.70**, explaining 70% of the variability in monthly case counts. The MAE of ~2 cases indicates that on average the model deviates by approximately 2 cases in its predictions, which is acceptable given the aggregated nature of the data.

## 🧪 Pipeline Developed

The pipeline implemented in Azure ML Designer includes the following components:

1. **Data Input** → Load dataset from Azure Data Asset
2. **Select Columns** → Select relevant features
3. **Clean Missing Data** → Missing value imputation
4. **Execute Python Script** → Feature engineering and temporal aggregation
5. **Split Data** → Train/test split (70/30)
6. **Linear Regression** → Regression model
7. **Train Model** → Model training
8. **Score Model** → Generate predictions
9. **Evaluate Model** → Calculate evaluation metrics

## 💡 Conclusions

- The linear regression model provides reasonable predictions for monthly hospital case counts
- Temporal features (Year, Month) along with diagnosis are useful indicators for prediction
- The R² of 0.70 suggests that probably need more data.
- Azure ML Designer enables efficient ML pipeline creation without extensive coding

## 📝 Additional Documentation

For detailed implementation instructions, see the PDF document included in this repository.
