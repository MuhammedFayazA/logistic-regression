# Data notes

## `diabetes.csv`
Pima Indians Diabetes dataset: 768 female patients of Pima Indian heritage, 8 clinical measurements and a binary diabetes outcome (268 positive, 500 negative). Originally from the National Institute of Diabetes and Digestive and Kidney Diseases and widely mirrored (UCI, Kaggle).

This copy was assembled from a public mirror of the headerless version, with the standard column names added:
`Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age, Outcome`.

Known quirk: `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin` and `BMI` use `0` for missing values. Notebook 1 handles this in its cleaning step.

## Credit card data (notebook 2)
Not stored in the repo. The notebook generates a seeded, simulated dataset (30,000 rows, 1.25% fraud) with the same columns as the Kaggle "Credit Card Fraud Detection" file. To use the real file, download it from Kaggle, place it in this folder and replace the generation cell with `data = pd.read_csv('../data/creditcard.csv')`. Note the real file has 284,807 rows and a far lower fraud rate (about 0.17%), so results will differ.

## `mtcars` (notebook 3)
The 32-row Motor Trend Car Road Tests dataset (1974), embedded directly in the notebook.
