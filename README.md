# OVERVIEW

Using dataset of credit card credit provided by the company **LendingClub**, a peer-to-peer lending services company, the purpose of this challenge is to employ `machine learning statistical algorithms` to predict Credit Risk.

The credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore in order to achieve our goal we will be utilizing six machine learning models to make predictions and evaluate these models in order to compare between them and conclude if we could adapt a suitable model or not. These machine learning models are:

- **Oversampling: RandomOverSampler**
- **Synthetic Minority Oversampling Technique: SMOTE**
- **Undersampling: ClusterCentrois**
- **Combination (over and under) sampling: SMOTEEN**
- **Ensemble Classifier: BalancedRandomForestClassifier**
- **Ensemble Classifier: EasyEnsembleClassifier**

# RESULTS

The target variable in our dataset is the `loan_status` it was neatly modified to a binary variable of values **high risk** and **low risk**.
The data was then split into training and testing sets using the default 75%-25% partition.

![splitting](/Images/splitting.PNG)

## Oversampling: RandomOverSampler

* **balanced accuracy score:** 65.7%

![bas](/Images/os_bas.PNG)

* **precision:**
    * high risk: 1%
    * low risk: 100%
* **recall:**
    * high risk: 71%
    * low risk: 60%
* **F1 score:**
    * high risk: 2%
    * low risk: 75%

![bas](/Images/os_cri.PNG)

## Synthetic Minority Oversampling Technique: SMOTE

* **balanced accuracy score:** 66.2%

![bas](/Images/s_bas.PNG)

* **precision:**
    * high risk: 1%
    * low risk: 100%
* **recall:**
    * high risk: 63%
    * low risk: 69%
* **F1 score:**
    * high risk: 2%
    * low risk: 82%

![bas](/Images/s_cri.PNG)

## Undersampling: ClusterCentrois

* **balanced accuracy score:** 54.4%

![bas](/Images/u_bas.PNG)

* **precision:**
    * high risk: 1%
    * low risk: 100%
* **recall:**
    * high risk: 69%
    * low risk: 40%
* **F1 score:**
    * high risk: 1%
    * low risk: 57%

![bas](/Images/u_cri.PNG)

## Combination (over and under) sampling: SMOTEEN

* **balanced accuracy score:** 64.5%

![bas](/Images/c_bas.PNG)

* **precision:**
    * high risk: 1%
    * low risk: 100%
* **recall:**
    * high risk: 72%
    * low risk: 57%
* **F1 score:**
    * high risk: 2%
    * low risk: 72%

![bas](/Images/c_cri.PNG)

## Ensemble Classifier: BalancedRandomForestClassifier

* **balanced accuracy score:** 78.7%

![bas](/Images/b_bas.PNG)

* **precision:**
    * high risk: 3%
    * low risk: 100%
* **recall:**
    * high risk: 69%
    * low risk: 88%
* **F1 score:**
    * high risk: 6%
    * low risk: 94%

![bas](/Images/b_cri.PNG)

## Ensemble Classifier: EasyEnsembleClassifier

* **balanced accuracy score:** 93.2%

![bas](/Images/n_bas.PNG)

* **precision:**
    * high risk: 9%
    * low risk: 100%
* **recall:**
    * high risk: 92%
    * low risk: 94%
* **F1 score:**
    * high risk: 16%
    * low risk: 97%

![bas](/Images/n_cri.PNG)

# SUMMARY

In order to compare these six models, we first need to chose a primary metric, if the purpose is to minimize the number of false positives (i.e., predicting that a borrower will default when they actually do not), precision should be the primary metric. On the other hand if the purpose is to minimize the number of false negatives (i.e., predicting that a borrower will not default when they actually do), we might need to consider using recall as the primary key.

Ultimately, the choice of which metric to use will depend on the specific needs and priorities of your application. It may also be helpful to consider using a metric that combines both precision and recall, i.e. the F1 score.

Hence, we're gonna use the F1 score for the high risk class as the primary metric for comparison. This is because correctly identifying high risk cases is likely to be more important for the lender, as it allows them to proactively manage risk and potentially prevent defaults.

The following is a summary table of the F1 score results for all six models

**Machine Learning Model** | **F1 score for high risk** 
| :--- | ---: 
RandomOverSampler  | 2% 
SMOTE  | 2%
ClusterCentroids  | 1% 
SMOTEEN  | 2% 
BalancedRandomForestClassifer  | 6% 
EasyEnsembleClassifer  | 16%

Observing these results we recommend the use of the `EasyEnsembleClassifer` model as it produces the highest F1 score for high risk.