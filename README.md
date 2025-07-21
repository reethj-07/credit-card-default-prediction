# Credit Card Default Prediction

## 🚀 Project Overview
[cite_start]This project focuses on developing a binary classification model to predict whether a credit card customer will default on their payment in the next month[cite: 306]. [cite_start]The primary goal is to minimize financial risk by accurately identifying potential defaulters, using a machine learning pipeline that includes exploratory data analysis, feature engineering, and model optimization[cite: 307].

---

## 📊 Key Findings from EDA

Exploratory Data Analysis revealed several behavioral and financial patterns linked to default risk:

* [cite_start]**Payment Delays are Critical**: Customers with a history of overdue payments (`PAY_x >= 1`) show a significantly higher likelihood of defaulting[cite: 354].
* [cite_start]**Credit Utilization**: Defaulters tend to have higher credit utilization ratios, meaning they use a larger portion of their available credit, which suggests financial overextension[cite: 427].
* **Credit Limit**: Default rates decrease as the credit limit increases. [cite_start]Customers with lower limits (e.g., 0-50K) have the highest default rates[cite: 497, 498].
* [cite_start]**Age**: Default rates tend to increase with age, with the 60-80 age group showing the highest risk[cite: 442, 443].
* [cite_start]**Payment Consistency**: Defaulters exhibit lower and less consistent payment amounts, indicating irregular repayment habits[cite: 478].

---

## 🛠️ Modeling Strategy

The modeling strategy was designed to handle the complexities of financial data and align with business needs:

1.  [cite_start]**Feature Engineering**: New features were created to enhance model performance, including `credit_utilization`, `payment_ratio`, and `delinquency_streak`[cite: 315, 316, 317].
2.  **Handling Class Imbalance**: The dataset was imbalanced, with only about 19% of customers defaulting. [cite_start]**SMOTE (Synthetic Minority Over-sampling Technique)** was used on the training data to create synthetic samples of the minority class (defaulters), improving the model's sensitivity[cite: 320, 321].
3.  [cite_start]**Model Comparison**: Several models were evaluated, including Logistic Regression, Decision Tree, Random Forest, XGBoost, and LightGBM[cite: 324].
4.  **Evaluation Metric**: The **F2-score** was prioritized, as it gives more weight to recall. [cite_start]This is crucial for minimizing false negatives (failing to predict a default), which is more costly for a financial institution[cite: 328, 581].
5.  [cite_start]**Final Model**: **Random Forest** was selected as the best model due to its superior F2-score (86.5%) and recall (85.1%) on the internal test set[cite: 578, 585, 586, 588].
6.  [cite_start]**Threshold Tuning**: The final classification threshold was tuned to **0.30**, which achieved the highest F2-score of 0.9033 on the validation set, making the model more sensitive to defaulters[cite: 593, 594].

---

## 📈 Business Implications
This predictive model offers significant business value:
* [cite_start]**Proactive Risk Management**: By identifying high-risk customers early, the bank can apply mitigation strategies like limit reductions or tailored communication to prevent losses[cite: 598, 604].
* [cite_start]**Reduced Financial Loss**: Prioritizing high recall minimizes the number of missed defaulters, directly protecting the bank from financial losses[cite: 597].
* [cite_start]**Data-Driven Decisions**: The model's reliance on behavioral features (like repayment ratios) provides clear, justifiable reasons for credit decisions[cite: 602].

---

## 📋 How to Run the Project
1.  Clone this repository to your local machine.
2.  Install the required libraries using pip:
    ```
    pip install -r requirements.txt
    ```
3.  Open and run the `notebook_submission__22112085.ipynb` file in a Jupyter environment. The notebook handles data loading, preprocessing, model training, and prediction.

---

## 📁 Files in This Repository
* `notebook_submission__22112085.ipynb`: The main Jupyter Notebook with all analysis and modeling code.
* `Credit_Card_Default_Report_Summary.pdf`: A summary report of the project findings.
* `train_dataset_final1.csv`: The training dataset.
* `validate_dataset_final.csv`: The validation dataset for final predictions.
* `requirements.txt`: A list of required Python libraries for reproducibility.