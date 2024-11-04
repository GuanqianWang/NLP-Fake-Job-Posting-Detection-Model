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
Under this workflow, using xgboost model, we have achieved the following precision, recall, and F1 score for the testing set:

|   | precision | recall | f1-score | support |   |   |   |   |   |   |   |   |
|---|-----------|--------|----------|---------|---|---|---|---|---|---|---|---|
| 0 | 0.98      | 1.00   | 0.99     | 1981    |   |   |   |   |   |   |   |   |
| 1 | 0.94      | 0.75   | 0.83     | 151     |   |   |   |   |   |   |   |   |

It achieved a total accuracy of 0.98, with the f1 score reaching 0.83 for the fraudulent cases. One can see that this model is rather conservative, but we consider this an appropriate model choice. In [this article](https://medium.com/@sohilsharma1996/real-fake-job-posting-prediction-e67eedfbccc4), the author achieved a similar f1 score, and more balanced precision and recall. (both are around 0.82) However, we consider it more important to keep precision high and improve recall as much as possible, this is because the number of real job postings is far bigger than fake job postings. Any minor sacrifice of precision means a very large number of real jobs are classified as fake jobs. We believe it's equally bad to incorrectly identify a real job as a fake one, or identify a fake job as a real one; and for the very imbalanced data (fake posting is very rare), aiming for a higher recall but losing precision is not cost-effective. Also, a recall of 0.75 is still well above 0.5, so it does not make the model defeated by some trivial models.
