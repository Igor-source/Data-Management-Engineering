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

