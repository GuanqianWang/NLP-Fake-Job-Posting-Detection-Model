# NLP-Fake-Job-Posting-Detection-Model
This project aims to select the most optimal model that can predict whether a job posting is real or fake. The data is mainly from the Kaggle challenge [Real / Fake Job Posting Prediction](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction/data).
The model used the following categorical features:
* employment_type
* telecommuting
* has_company_logo
* required_experience
* required_education
* State
* Industry
* function
<!-- -->
The model used the following features as text features:
* company_profile
* description
* benefits
<!-- -->
The text features are tokenized using the following methods:
* TD IDF
* BERT (under testing)
* Open AI embedding models (under testing)
# The overall workflow
The overall process of data loading, train test split, tokenization, and model fitting is provided by this file:
[Overall workflow showcase](https://github.com/GuanqianWang/NLP-Fake-Job-Posting-Detection-Model/blob/main/Workflow_showcase.ipynb). 
Under this workflow, using xgboost model, we have achieved the following precision, recall, and F1 score for the testing set:\

|   | precision | recall | f1-score | support |   |   |   |   |   |   |   |   |
|---|-----------|--------|----------|---------|---|---|---|---|---|---|---|---|
| 0 | 0.98      | 1.00   | 0.99     | 1981    |   |   |   |   |   |   |   |   |
| 1 | 0.94      | 0.75   | 0.83     | 151     |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
|   |           |        |          |         |   |   |   |   |   |   |   |   |
