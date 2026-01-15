# Fraud Detection Analysis

> 📊 **[View Presentation](presentations/fraud_detection_presentation.pdf)** | 📓 [Notebooks](#notebooks) | 📁 [Data](#data-files)

## Project Overview

This project presents a comprehensive fraud detection analysis using machine learning techniques to identify fraudulent activities and optimize business decision-making. The analysis is divided into two main components:

1. **Anomaly Detection**: Identifying temporal anomalies in fraud patterns and investigating root causes
2. **Fraud Detection Models**: Building and optimizing ML models with and without FraudKiller features to maximize business profitability

## Objectives

- Detect anomalies in fraud rates over time using time-series analysis
- Investigate potential root causes of fraud spikes during anomalous periods
- Develop and compare multiple machine learning models for fraud detection
- Optimize decision thresholds to maximize business profit while maintaining effective fraud detection
- Evaluate the impact of FraudKiller features on model performance

## Methodology

### Data Preprocessing
- **Missing Value Handling**: KNN imputation for credit scores and fraud scores, mean/mode imputation for other features
- **Data Quality**: Identified and corrected logical inconsistencies (e.g., transaction dates before application dates)
- **Feature Engineering**: Created temporal features (hour, day_of_week, week_of_year), handled categorical encoding, standardized numerical features

### Anomaly Detection
- **Time-Series Analysis**: Daily aggregation of fraud metrics (fraud rate, approval rate, application volume)
- **Isolation Forest**: Unsupervised anomaly detection to identify unusual patterns
- **Root Cause Analysis**: Comparative analysis of feature distributions during normal vs. anomalous periods

### Model Development
- **Algorithms Evaluated**: Logistic Regression, Random Forest, XGBoost
- **Hyperparameter Tuning**: Grid Search Cross-Validation for optimal parameters
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1-score, Confusion Matrices

### Business Optimization
- **Profit Maximization**: Optimized decision thresholds using scipy.optimize
- **Three-Tier Decision System**: Auto-approve, Manual Review, and Decline based on fraud probability thresholds
- **Cost-Benefit Analysis**: Balanced revenue, fraud losses, manual review costs, and vendor costs

## Key Findings

### 1. Anomaly Detection Results
- **Anomalous Period Identified**: June 25 - July 4, 2019
- **Pattern**: Coordinated fraud campaign with increased fraud rates, unusual credit/fraud score patterns, and elevated application volumes
- **Isolation Forest**: Successfully detected 11 anomalous days in the time-series data

### 2. Model Performance
- **Best Model**: XGBoost
  - Without FraudKiller: **98% accuracy**
  - With FraudKiller: **96% accuracy**
- **Model Comparison**:
  - XGBoost: 96-98% accuracy
  - Random Forest: 86-91% accuracy
  - Logistic Regression: 76-78% accuracy

### 3. Business Impact
- **Profit Optimization**: Successfully optimized decision thresholds to maximize business profit
- **FraudKiller Evaluation**: Assessed trade-offs between model accuracy and business outcomes with/without FraudKiller features

## Technical Stack

- **Python Libraries**: pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn, scipy
- **Machine Learning**: Logistic Regression, Random Forest, XGBoost, Isolation Forest
- **Optimization**: scipy.optimize for threshold optimization
- **Data Processing**: KNN imputation, feature scaling, one-hot encoding

## Project Structure

```
FraudDetection/
├── 01_Anomaly_Detection_Analysis.ipynb  # Part 1: Data exploration & anomaly detection
├── 02_Fraud_Detection_Models.ipynb       # Part 2: Model development & optimization
├── FraudDetection.ipynb                   # Original combined notebook (backup)
├── README.md                              # Project documentation
├── SETUP.md                               # Setup instructions
├── NOTEBOOK_STRUCTURE.md                  # Notebook organization guide
├── .gitignore                             # Git ignore file
├── presentations/                         # Presentation materials
│   ├── fraud_detection_presentation.pdf  # Main presentation slides
│   └── README.md                          # Presentation documentation
└── data/
    ├── raw/                               # Raw data files
    │   ├── fraud_detection_dataset_part1.xlsx
    │   └── fraud_detection_dataset_part2.xlsx
    └── cleaned/                           # Processed/cleaned datasets (generated)
        ├── fraud_detection_cleaned.xlsx
        └── fraud_detection_processed_part2.csv
```

## Notebooks

- **`01_Anomaly_Detection_Analysis.ipynb`**: Part 1 - Data exploration, cleaning, and anomaly detection
- **`02_Fraud_Detection_Models.ipynb`**: Part 2 - Feature engineering, model development, and optimization
- **`FraudDetection.ipynb`**: Original combined notebook (backup)

## Data Files

## How to Use

1. **Prerequisites**: Install required libraries
   ```bash
   pip install pandas numpy scikit-learn xgboost matplotlib seaborn scipy openpyxl
   ```

2. **Data Files**: The raw datasets are located in `data/raw/`:
   - `data/raw/fraud_detection_dataset_part1.xlsx` (Part 1 - Anomaly Detection)
   - `data/raw/fraud_detection_dataset_part2.xlsx` (Part 2 - Fraud Detection Models)
   
   Cleaned/processed datasets are automatically saved to `data/cleaned/` during notebook execution:
   - `data/cleaned/fraud_detection_cleaned.xlsx` (Part 1 cleaned data)
   - `data/cleaned/fraud_detection_processed_part2.csv` (Part 2 processed data)

3. **Run Analysis**: 
   - **Part 1**: Open `01_Anomaly_Detection_Analysis.ipynb` and run cells sequentially
   - **Part 2**: Open `02_Fraud_Detection_Models.ipynb` after completing Part 1
   - Alternatively, use the original `FraudDetection.ipynb` for the complete analysis in one notebook

4. **View Presentation**: Check `presentations/fraud_detection_presentation.pdf` for a comprehensive overview of the project

5. **Customization**: Adjust hyperparameters, thresholds, or add new features as needed

## Results Summary

- **Anomaly Detection**: Successfully identified fraud spike period (June 25 - July 4, 2019)
- **Model Accuracy**: Achieved 98% accuracy with XGBoost model
- **Business Optimization**: Optimized thresholds for maximum profit considering all cost factors
- **Feature Impact**: Evaluated FraudKiller features' contribution to model performance

## Future Work

1. **Enhanced Features**: Incorporate additional data sources (user behavior, transaction history, device fingerprints)
2. **Real-time Deployment**: Implement model monitoring and feedback loops for continuous improvement
3. **Advanced Techniques**: Explore ensemble methods, deep learning, or graph-based approaches
4. **A/B Testing**: Validate model performance in production with controlled experiments
5. **Explainability**: Add model interpretability tools (SHAP, LIME) for better understanding of fraud patterns

## Author

Data Science / Machine Learning Engineering Project

## License

This project is for educational and portfolio purposes.
