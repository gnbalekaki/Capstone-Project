### Capstone Project: ML Model to detect credit card Fraud transactions (Final Report - Part 2). 

Author: **Gerald Balekaki**

#### Executive summary
There is a lack of public available datasets on financial services and specially in the emerging mobile money transactions domain. Financial datasets are important to many researchers and in particular to us performing research in the domain of fraud detection. Part of the problem is the intrinsically private nature of financial transactions, that leads to no publicly available datasets.

We present a synthetic dataset generated using the simulator called PaySim as an approach to such a problem. PaySim uses aggregated data from the private dataset to generate a synthetic dataset that resembles the normal operation of transactions and injects malicious behaviour to later evaluate the performance of fraud detection methods.

#### Rationale
o	Fraud detection in credit card transactions is critical for preventing financial losses, protecting consumers from identity theft, and ensuring the integrity of financial systems. A robust fraud detection system enhances the security of digital transactions and helps businesses build trust with their customers by providing timely alerts for potential fraudulent activity.

#### Research Question
o	How can we easily classify credit card transactions as fraudulent or non-fraudulent based on transaction attributes such as amount, location, and time?

#### Data Sources
o	Our data is sourced from publicly available datasets such as the **Kaggle Credit Card Fraud Detection dataset**.
  - Refer to the link:  https://www.kaggle.com/datasets/ealaxi/paysim1
    
##### How to Download the Dataset
-  Use the Google Drive link provided below to download the CSV dataset. Once downloaded, unzip and copy the file into the data folder within the project repository.
  -  https://drive.google.com/file/d/1FAnOsdPhlpeeZ7MUmH96fzyOe2tOD25V/view?usp=drive_link (Note: This approach is necessary due to GitHub’s upload limit of 100MB, whereas our dataset is approximately 480MB).*

#### Methodology

We followed a step-by-step process to solve the machine learning classification problem, guided by the standardized CRISP-DM framework. We began by understanding the business problem under analysis. This was followed by exploratory data analysis, which includes data cleaning and preprocessing—such as handling categorical variables.

Next, we train and model the data using a variety of supervised learning algorithms, including Logistic Regression, Decision Trees, Support Vector Machines (SVM), k-Nearest Neighbors (KNN), and Neural Networks. Hyperparameter tuning is performed using GridSearchCV, along with stratified 5-fold cross-validation to ensure robustness.

Each model is evaluated individually based on performance metrics under different parameter configurations. Additionally, we explore anomaly detection techniques to address class imbalance. Model performance is assessed using evaluation metrics such as the classification report and confusion matrix, focusing on precision, accuracy score, recall, and F1-score. Finally, we conclude by summarizing key insights and interesting findings from our analysis. 

#### Results
In our preliminary study, we examined the “creditFraud” dataset, which contains 6,362,620 records across 11 features, including integer, object, and float data types. Due to the dataset’s size, we sampled 50,000 records for model training, but our visualizations reflect the entire dataset.

The target variable is “isFraud”, where 0 represents legitimate transactions and 1 indicates fraudulent ones. The class distribution is highly imbalanced, with 99.88% of transactions being legitimate and only 0.012% labeled as fraud. This imbalance is clearly illustrated in our class distribution plot. We also visualized the transaction amount distribution, highlighting the sparse but significant presence of fraudulent transactions (shown as red dots).

In addition, we compared the “isFraud” and “isFlaggedFraud” fields to understand the overlap. Out of 8,213 transactions labeled as fraud, only 16 were flagged as such, and all 16 were indeed fraudulent—none were false positives. Interestingly, 13 of these 16 flagged frauds involved large transaction amounts, suggesting a pattern. Only 3 involved amounts below 5 million (refer to the red dots in our transaction amount distribution plot), indicating that large transactions may be a key fraud indicator.

We trained several popular classification models tailored for binary classification, including Decision Tree, k-NN, Naive Bayes, Logistic Regression, SVM, and Neural Networks. Most classifiers, with optimized hyperparameters via GridSearchCV, performed exceptionally well—achieving around 99.9% accuracy in both cross-validation (with negligible variance) and test performance, showing strong generalization.

In contrast, the Naive Bayes classifier showed moderate performance. With its best hyperparameter (var_smoothing = 1e-07), it achieved a cross-validation accuracy of 69.4% (±6.7%) and a test accuracy of 66.0%. The higher standard deviation in CV results suggests sensitivity to data splits, and the lower test accuracy implies challenges with generalization.

#### Interpretation of Results
Our models performed exceptionally well, suggesting that the dataset is either very clean or that the differences between normal and fraudulent transactions are relatively easy to detect. However, when a model achieves near-perfect accuracy, it’s important to verify that it isn't relying on overly obvious or “too easy” clues—this can occur if there’s a hidden correlation between the input features and the target variable, making the task unrealistically simple.

In the real world, fraud is rare because it’s costly and often quickly reported or blocked. As a result, the majority of transactions are legitimate. This makes it realistic for our model to predominantly predict “not fraud,” as it mirrors actual transaction patterns.

One of the models we tested, Naive Bayes, performed poorly—misclassifying about one-third of the transactions. This highlights a key limitation: Naive Bayes assumes feature independence, which likely doesn’t apply to our dataset. In contrast, models like Logistic Regression and SVMs, which don’t make this assumption, performed significantly better and are more appropriate for this task.

In summary, our top-performing models achieved over 99% accuracy, demonstrating strong potential for reliable fraud detection. Such performance can greatly enhance digital transaction security by quickly and accurately flagging suspicious activity—benefiting both businesses and consumers. These results align well with the original goals of our project.


#### Recommendation
We recommend conducting additional tests, particularly to evaluate how often legitimate transactions are incorrectly flagged as fraud (false positives) or fraudulent ones are missed (false negatives). When a model appears too perfect, it's important to investigate further to ensure its performance is realistic and not due to data artifacts. We may also explore simpler models to see if they can achieve comparable results with less complexity.


##### Contact and Further Information
  **Gerald Balekaki**
  *Email: gnbalekaki@gmail.com*
