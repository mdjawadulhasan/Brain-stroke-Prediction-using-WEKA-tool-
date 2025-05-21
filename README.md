# Brain Stroke Classification

## Project Overview
This project develops machine learning models to predict the likelihood of brain stroke based on various health and demographic attributes. Stroke occurs when there is insufficient blood supply to the brain, which can be ischemic (lack of blood flow) or hemorrhagic (bleeding). By analyzing factors such as blood pressure, hypertension, heart disease, and other risk factors, our models aim to provide early prediction that could potentially help in preventive care.

## Dataset
The dataset contains information about 4981 patients with 10 attributes plus a target variable:

- **gender**: Male/Female (52% Male, 48% Female)
- **age**: Numeric value
- **hypertension**: Binary (0: No, 1: Yes)
- **heart_disease**: Binary (0: No, 1: Yes)
- **ever_married**: "Yes" or "No" (74% married, 26% not married)
- **work_type**: Type of occupation (nominal)
- **Residence_type**: Urban/Rural (nominal)
- **avg_glucose_level**: Numeric value
- **bmi**: Body Mass Index (numeric)
- **smoking_status**: Nominal with some "unknown" values
- **stroke**: Target variable (0: No stroke, 1: Stroke)

Dataset source: [Kaggle - Brain Stroke Dataset](https://www.kaggle.com/datasets/zzettrkalpakbal/full-filled-brain-stroke-dataset?select=full_filled_stroke_data+%281%29.csv)

## Methodology

### Data Preprocessing
- Converted all continuous attributes to categorical values for compatibility with Naive Bayes
- Dropped less relevant attributes (ever_married, work_type, and Residence_type)

### Classification Models
We implemented and compared three different classification algorithms:

1. **Naive Bayes**
   - K-fold Cross-validation (K=10): 92.93% accuracy
   - Train-Test Split (80-20): 93.47% accuracy

2. **Decision Tree**
   - K-fold Cross-validation (K=10): 95.02% accuracy
   - Train-Test Split (80-20): 94.77% accuracy

3. **K-Nearest Neighbors (K=4)**
   - K-fold Cross-validation (K=10): 94.20% accuracy
   - Train-Test Split (80-20): 93.77% accuracy

## Results and Discussion
The Decision Tree algorithm with K-fold cross-validation (K=10) achieved the highest accuracy at 95.02%. However, all models showed a high number of False Negatives, which is particularly concerning in a medical context as these represent missed stroke predictions.

Analysis of the confusion matrices revealed:
- Decision Tree (best model):
  - True Negatives: 4733
  - False Positives: 0
  - True Positives: 248
  - False Negatives: 0
  - Some instances may remain unclassified due to missing branches in the tree

The dataset exhibits class imbalance which affects the model performance and reliability of the accuracy metric.

## Future Work
- Address class imbalance issues using techniques like SMOTE or class weighting
- Explore additional algorithms beyond the three implemented
- Incorporate feature importance analysis to identify the most predictive factors
- Optimize hyperparameters further
- Consider metrics beyond accuracy (like F1-score, recall) that may be more relevant for medical diagnostics


## Acknowledgments
This project was completed as part of the DATA WAREHOUSING AND DATA MINING course at American International University-Bangladesh (AIUB), under the supervision of DR. AKINUL ISLAM JONY.
