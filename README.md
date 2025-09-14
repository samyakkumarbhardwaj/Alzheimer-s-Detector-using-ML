Alzheimer's Disease Detection using Machine Learning

Project Summary

This project demonstrates an end-to-end machine learning solution for detecting Alzheimer's disease (AD) using a dataset of patient health metrics. The goal is to build an accurate yet highly explainable model that can be used to identify potential signs of AD. The project includes:

A Python script that trains a machine learning model.

A simplified web application (HTML, CSS, JavaScript) that serves as an interactive demonstration.

A comprehensive project report outlining the methodology and results.

The Problem
Alzheimer's disease is a progressive neurodegenerative disorder. Early detection is crucial for effective intervention and management. Machine learning offers a powerful way to analyze complex patient data—including clinical, demographic, and medical imaging features—to predict the likelihood of dementia.

Methodology
The project follows a standard machine learning workflow, with a strong focus on a simple and explainable model.

1. Dataset
The project uses the OASIS Longitudinal MRI Dataset, a publicly available dataset from Kaggle containing patient information such as age, years of education, and key clinical and imaging scores.

2. The Machine Learning Model
We use a Logistic Regression model for classification. This model was chosen specifically for its high level of explainability. Unlike complex "black box" models, Logistic Regression provides coefficients for each feature, which directly indicates how much a feature influences the prediction.

3. The Pipeline Path
To ensure the process is robust and reproducible, we use a scikit-learn pipeline. This pipeline automates the entire workflow:

Preprocessor: The data is first sent to a ColumnTransformer.

Numerical Features: Missing values in columns like MMSE are filled with the median, and the data is scaled using StandardScaler to ensure all features are on a similar scale.

Categorical Features: The M/F column is handled by an imputer that fills missing values with the most frequent gender.

Classifier: The preprocessed data is then passed to the Logistic Regression model, which is trained to make a prediction.

This pipeline ensures that the exact same preprocessing steps are applied to both the training data and any new data used for prediction, preventing errors and ensuring consistency.

How to Run the Project
Python Code
Ensure you have Python installed.

Install the required libraries: pip install pandas scikit-learn numpy

Download the oasis_longitudinal.csv dataset from Kaggle and place it in the same directory as the Python file.

Run the Python script from your terminal: python alzheimer_detector.py

Web Application
The web application is a single HTML file that serves as a demo for the project.

Open the alzheimer_detector.html file in any modern web browser (like Chrome or Firefox).

The JavaScript code within the file simulates the model's logic, allowing for an interactive demonstration without a backend server.

Project Explainability
A core objective of this project is explainability. The Logistic Regression model makes this possible by providing a coefficient for each feature.

A positive coefficient means the feature increases the likelihood of a "Demented" prediction.

A negative coefficient means the feature decreases the likelihood of a "Demented" prediction.

By analyzing these coefficients, we can clearly show which factors—such as age, MMSE score, or brain volume—are the most significant indicators in the model's decision-making process. This transparency is crucial for a medical application and makes the project easy to explain to a non-technical audience.