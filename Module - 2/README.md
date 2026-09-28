# Analytics Pipeline

`01_eda.py` is the profiling/cleaning stage. It records missing-value percentages before applying the assignment's threshold rule, creates the required plots, reports IQR outliers and fare distribution statistics, calculates the exact six-column correlation matrix, and saves the cleaned dataset.

`02_modeling.py` reads `outputs/cleaned_titanic.csv`, performs the stratified split before preprocessing, and keeps all preprocessing inside scikit-learn pipelines. The SMOTE comparison uses the imbalanced-learn pipeline so oversampling happens only on training folds. The Random Forest grid search explicitly uses `oob_score=True`.

The committed `titanic.csv` is the offline grading copy. In a normal connected run, the EDA script refreshes it from `sns.load_dataset('titanic')` exactly once and the modeling script never calls the seaborn loader.
