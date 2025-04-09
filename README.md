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

Next, we train and model the data using a variety of supervised learning algorithms, including Logistic Regression, Decision Trees, Random Forests, Support Vector Machines (SVM), k-Nearest Neighbors (KNN), and Neural Networks. Hyperparameter tuning is performed using GridSearchCV, along with stratified 5-fold cross-validation to ensure robustness.

Each model is evaluated individually based on performance metrics under different parameter configurations. Additionally, we explore anomaly detection techniques to address class imbalance. Model performance is assessed using evaluation metrics such as the classification report and confusion matrix, focusing on precision, recall, and F1-score. Finally, we conclude by summarizing key insights and interesting findings from our analysis. 

#### Results
What did your research find?

#### Next steps
What suggestions do you have for next steps?

#### Outline of project

- [Link to notebook 1]()
- [Link to notebook 2]()
- [Link to notebook 3]()


##### Contact and Further Information
