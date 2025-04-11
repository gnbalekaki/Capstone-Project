### ML Model to detect credit card Fraud transactions. 

**Gerald Balekaki**

#### Executive summary
There is a lack of public available datasets on financial services and specially in the emerging mobile money transactions domain. Financial datasets are important to many researchers and in particular to us performing research in the domain of fraud detection. Part of the problem is the intrinsically private nature of financial transactions, that leads to no publicly available datasets.

We present a synthetic dataset generated using the simulator called PaySim as an approach to such a problem. PaySim uses aggregated data from the private dataset to generate a synthetic dataset that resembles the normal operation of transactions and injects malicious behaviour to later evaluate the performance of fraud detection methods.

#### Rationale
o	Fraud detection in credit card transactions is critical for preventing financial losses, protecting consumers from identity theft, and ensuring the integrity of financial systems. A robust fraud detection system enhances the security of digital transactions and helps businesses build trust with their customers by providing timely alerts for potential fraudulent activity.

#### Research Question
o	How can we classify credit card transactions as fraudulent or non-fraudulent based on transaction attributes such as amount, location, and time?

#### Data Sources
o	The data will be sourced from publicly available datasets such as the **Kaggle Credit Card Fraud Detection dataset**, or, with proper authorization, transaction data from financial institutions.
  - Refer to the link:  https://www.kaggle.com/datasets/ealaxi/paysim1
    

#### Methodology

We follow a step-by-step process to solve the machine learning classification problem, guided by the standardized CRISP-DM framework. We begin by understanding the business problem under analysis. This is followed by exploratory data analysis, which includes data cleaning and preprocessing—such as handling categorical variables.

Next, we train and model the data using a variety of supervised learning algorithms, including Logistic Regression, Decision Trees, Support Vector Machines (SVM), k-Nearest Neighbors (KNN), and Neural Networks. Hyperparameter tuning is performed using GridSearchCV, along with stratified 5-fold cross-validation to ensure robustness.

Each model is evaluated individually based on performance metrics under different parameter configurations. Additionally, we explore anomaly detection techniques to address class imbalance. Model performance is assessed using evaluation metrics such as the classification report and confusion matrix, focusing on precision, recall, and F1-score. Finally, we conclude by summarizing key insights and interesting findings from our analysis. 

#### Results
In our preliminary study, we examined the “creditFraud” dataset, which contains 6,362,620 records across 11 features, including integer, object, and float data types. Due to the dataset’s size, we sampled 50,000 records for model training, but our visualizations reflect the entire dataset.

The target variable is “isFraud”, where 0 represents legitimate transactions and 1 indicates fraudulent ones. The class distribution is highly imbalanced, with 99.88% of transactions being legitimate and only 0.012% labeled as fraud. This imbalance is clearly illustrated in our class distribution plot. We also visualized the transaction amount distribution, highlighting the sparse but significant presence of fraudulent transactions (shown as red dots).

In addition, we compared the “isFraud” and “isFlaggedFraud” fields to understand the overlap. Out of 8,213 transactions labeled as fraud, only 16 were flagged as such, and all 16 were indeed fraudulent—none were false positives. Interestingly, 13 of these 16 flagged frauds involved large transaction amounts, suggesting a pattern. Only 3 involved amounts below 5 million (as shown in our transaction amount distribution plot), indicating that large transactions may be a key fraud indicator.

We trained several popular classification models tailored for binary classification, including Decision Tree, k-NN, Naive Bayes, Logistic Regression, SVM, and Neural Networks. Most classifiers, with optimized hyperparameters via GridSearchCV, performed exceptionally well—achieving around 99.9% accuracy in both cross-validation (with negligible variance) and test performance, showing strong generalization.

In contrast, the Naive Bayes classifier showed moderate performance. With its best hyperparameter (var_smoothing = 1e-07), it achieved a cross-validation accuracy of 69.4% (±6.7%) and a test accuracy of 66.0%. The higher standard deviation in CV results suggests sensitivity to data splits, and the lower test accuracy implies challenges with generalization.

#### Next steps
We suggest running a few more tests, especially to check how often transactions are wrongly flagged as fraud or missed. It’s worth looking deeper when a model seems too perfect. We might also try simpler models if they perform just as well. Finally, we plan to present our findings in a clear way that both technical and non-technical audiences can understand, and connect them back to our main research question.


##### Contact and Further Information
  **Gerald Balekaki**
  *Email: gnbalekaki@gmail.com*
