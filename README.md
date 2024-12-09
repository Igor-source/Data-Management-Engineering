# Introduction
When developing drugs, it is important to consider not only their biological activity, but also their physicochemical properties, such as stability and
reactivity. One of the key parameters that allows us to evaluate these properties is the HOMO-LUMO gap. The lower this value, the less stable the
compound, which can affect its synthesis and practical application.

# QM9.csv
QM9 is a dataset widely used in computational chemistry and machine learning to study molecular properties. All molecules in it are made up of carbon (C), hydrogen (H), nitrogen (N), oxygen (O), and fluorine (F) atoms. Each molecule is represented based on quantum mechanical calculations.

## Properties
| Sign  | Definition |
| ------------- | ------------- |
|μ:  | Dipole moment.|
|α:  |Polarizability.|
|HOMO / LUMO: |Orbital energies.|
|Gap: |Difference between HOMO and LUMO.|
|E_0: |Internal energy.|
|Cv: |Heat capacity.|

## Purpose:
Clean and prepare the data in Jupyter Notebook so that it is suitable for loading and using in a machine learning model.

## Tasks
1. Extract descriptors from Mordred и RdKit
2. Data curation
3. Drop duplicate
4. Feature selection
5. Feature Transformation
6. Stores the results in a PostgreSQL database
7. Model

## Project Structure
```
project_root/
│
├── Split_Mordred_set/       # Split into multiple CSV files due to large size. Contains all descriptors from the Mordred library.
├── Split_data_Merged_data/  # Split into multiple CSV files due to large size. This is the merged dataset of Mordred, RdKit, and new_qm9 descriptors.
├── .gitignore               # Specifies intentionally untracked files to ignore.
├── Merged_data2.csv         # A merged dataset in CSV format.
├── NewDataset.csv           # A new dataset generated for analysis.
├── Project1.ipynb           # Extracting descriptors from Mordred and RdKit.
├── Project2.ipynb           # Feature selection methods: Pearson correlation and visualization.
├── Project3.ipynb           # Data curation: encoding categorical data, detecting outliers.
├── Project4 (1).ipynb       # Feature transformation methods: PCA and t-SNE.
├── Project5.ipynb           # Demonstration of additional data processing methods using t-SNE.
├── Project6.ipynb           # Model training with XGBoost and LightGBM.
├── README.md                # Project documentation.
├── RdKitSet.csv             # Dataset containing RdKit descriptors.
├── Without_HOMO_LUMO.csv    # Final dataset prepared for PostgreSQL database upload.
├── new_qm9.csv              # The original dataset used initially.
├── split_csv.ipynb          # Script to split large datasets into smaller parts.
└── transformed_df.csv       # Dataset after normalization and dimensionality reduction.
```

Вот текст с сохранённой разметкой и переводом:

## 🚀 Getting Started
To start working on the project, you need to create a separate environment. To do this, run the following command in the terminal.  
```
conda env export > environment.yml
```
Then create the environment based on `environment.yml`:  
```
conda env create -f environment.yml
```

## Чистка датасета и обучение модели  
For molecule optimization:  
- Use the model to predict the gap of new molecules.  
- Based on the importance of descriptors, change key parameters (e.g. cyclicity,  
mass) to obtain molecules with the desired gap.  

For model selection:  
LightGBM is better because it:  
- Predicts more accurately (lower MSE, RMSE, MAE).  
- Learns faster.  
- Explains data better (high R²).  

## Загрузка данных в PostgreSQL  
To do this, you need to install the `psycopg2` library:  
```
conda install psycopg2
```  
After that, you need to connect to the server using the following details:  
```
pgconn = psycopg2.connect(
    host='localhost',
    user='postgres',
    password='123456QWERTY',
    database='postgres')
```
Данные можно увидеть войдя в pgAdmin 4 и введя данные, которые находятся выше. После введите следующий SQL запрос
```
Select * from my_table LIMIT 10
```
Remember: This is a learning tool, not a production-ready solution. Use it to understand concepts and build your own improved versions!

