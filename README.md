# Big Mart Sales Prediction

## Project Overview
This project predicts **Item Outlet Sales** using machine learning on the Big Mart sales dataset. The provided notebook performs data loading, missing-value handling, exploratory data analysis, categorical feature encoding, train-test splitting, XGBoost model training, and evaluation using R² score.

## Dataset
The notebook uses `Train.csv` as the dataset.

- Records: **8,523**
- Original features: **11**
- Target column: `Item_Outlet_Sales`
- Missing values found:
  - `Item_Weight`: 1,463
  - `Outlet_Size`: 2,410

`Test.csv` is included as a project resource because it was provided with the project files. The provided notebook itself trains and evaluates the model using a train/test split created from `Train.csv`.

## Data Preprocessing
The notebook performs the following preprocessing steps:

1. Loads `Train.csv` using Pandas.
2. Checks dataset structure and missing values.
3. Fills missing `Item_Weight` values using the mean.
4. Handles missing `Outlet_Size` values based on `Outlet_Type`.
5. Standardizes inconsistent `Item_Fat_Content` values:
   - `low fat` → `Low Fat`
   - `LF` → `Low Fat`
   - `reg` → `Regular`
6. Converts categorical features into numerical values using `LabelEncoder`.
7. Separates features (`X`) and target (`Y`).
8. Splits the data into training and testing sets using an 80:20 split with `random_state=2`.

## Machine Learning Model
**XGBoost Regressor (`XGBRegressor`)** is used to predict `Item_Outlet_Sales`.

### Data Split
- Total records: 8,523
- Training records: 6,818
- Testing records: 1,705

## Model Evaluation

| Dataset | R² Score |
|---|---:|
| Training | **87.51%** |
| Testing | **51.56%** |

The evaluation metric used in the notebook is the **R² (R-squared) score**.

## Exploratory Data Analysis
The notebook includes analysis and visualizations for:

- Item Weight distribution
- Item Visibility distribution
- Item MRP distribution
- Item Outlet Sales distribution
- Outlet Establishment Year
- Item Fat Content
- Item Type
- Outlet Size

## Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook / Google Colab

## Project Files
- `Big_Mart_Sales_Prediction_FINAL.ipynb` — executed project notebook
- `Train.csv` — training dataset used by the notebook
- `Test.csv` — provided test dataset
- `requirements.txt` — required Python libraries
- `README.md` — project documentation
- Project presentation (`.pptx`) — project overview and results

## How to Run

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Open the notebook
Open `Big_Mart_Sales_Prediction_FINAL.ipynb` in Jupyter Notebook or Google Colab.

### 3. Add the dataset
Keep `Train.csv` in the expected project location and update the file path if required.

### 4. Run the notebook
Run the cells sequentially to perform preprocessing, analysis, model training, and evaluation.

## Project Objective
The objective is to build a regression model that can learn from item and outlet characteristics and predict the sales value of an item at a particular outlet.

## Result
The implemented XGBoost Regressor achieved an R² score of **87.51% on the training split** and **51.56% on the testing split** created from `Train.csv`.
