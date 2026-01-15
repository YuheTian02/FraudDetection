# Setup Guide

## Project Structure

The project is organized with a clear data directory structure:

```
FraudDetection/
├── data/
│   ├── raw/              # Raw datasets (already uploaded)
│   │   ├── fraud_detection_dataset_part1.xlsx
│   │   └── fraud_detection_dataset_part2.xlsx
│   └── cleaned/          # Cleaned/processed datasets (generated automatically)
│       ├── fraud_detection_cleaned.xlsx
│       └── fraud_detection_processed_part2.csv
├── FraudDetection.ipynb  # Main analysis notebook
├── README.md             # Project documentation
└── .gitignore           # Git ignore file
```

## Data Files

### Raw Data (Already Uploaded)
- **`data/raw/fraud_detection_dataset_part1.xlsx`**: Part 1 dataset for anomaly detection analysis
- **`data/raw/fraud_detection_dataset_part2.xlsx`**: Part 2 dataset for fraud detection model development

### Cleaned Data (Generated Automatically)
The notebook automatically saves cleaned/processed datasets to `data/cleaned/`:
- **`data/cleaned/fraud_detection_cleaned.xlsx`**: Part 1 cleaned dataset (after imputation and data quality fixes)
- **`data/cleaned/fraud_detection_processed_part2.csv`**: Part 2 processed dataset (after feature engineering, encoding, and scaling)

## Running the Analysis

1. **Prerequisites**: Install required libraries
   ```bash
   pip install pandas numpy scikit-learn xgboost matplotlib seaborn scipy openpyxl
   ```

2. **Open the Notebook**: 
   ```bash
   jupyter notebook FraudDetection.ipynb
   ```

3. **Run the Analysis**: 
   - Execute cells sequentially
   - The notebook will:
     - Load raw data from `data/raw/`
     - Perform data cleaning and feature engineering
     - Automatically save cleaned datasets to `data/cleaned/`
     - Run analysis and generate results

## Data Processing Flow

1. **Part 1 (Anomaly Detection)**:
   - Loads `data/raw/fraud_detection_dataset_part1.xlsx`
   - Performs KNN imputation for missing values
   - Fixes data quality issues
   - Saves cleaned data to `data/cleaned/fraud_detection_cleaned.xlsx`

2. **Part 2 (Fraud Detection Models)**:
   - Loads `data/raw/fraud_detection_dataset_part2.xlsx`
   - Performs feature engineering (encoding, scaling, imputation)
   - Saves processed data to `data/cleaned/fraud_detection_processed_part2.csv`

## Git Configuration

The `.gitignore` file is configured to:
- Track data files by default (commented out data exclusions)
- Ignore Python cache files, Jupyter checkpoints, and OS files

If you want to exclude data files from Git (e.g., for large files or sensitive data):
1. Uncomment the data-related lines in `.gitignore`
2. Consider using Git LFS for large files:
   ```bash
   git lfs install
   git lfs track "*.xlsx"
   git lfs track "*.csv"
   ```

## Notes

- The cleaned datasets are generated automatically when you run the notebook
- You can reload cleaned datasets directly if you want to skip the cleaning steps
- All file paths in the notebook are relative to the project root directory
