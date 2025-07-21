# Credit Card Default Prediction

## 🚀 Project Overview
This project presents a binary classification model developed to predict whether a credit card customer will default on their payment in the next month. The solution focuses on minimizing the financial risk of missed defaulters by using a structured machine learning pipeline, from data analysis to model deployment.

---

## 🛠️ Approach and Modeling Strategy
The project followed a systematic approach to ensure robust and reliable predictions:

1.  **Data Understanding & EDA**: The process started with a comprehensive analysis of customer behavior, financial patterns, and variable distributions to understand the dataset. Key insights were derived from exploring correlations between demographics, repayment status, and billing amounts.

2.  **Feature Engineering**: To improve model performance, new features were engineered, including the credit utilization ratio, repayment-to-bill ratios, average bill amounts, and delinquency patterns based on repayment history (`pay_0` to `pay_6`).

3.  **Handling Class Imbalance**: As only about 19% of customers in the dataset defaulted, the class imbalance was addressed using **SMOTE (Synthetic Minority Over-sampling Technique)**. This technique generated synthetic samples for the minority class (defaulters) to improve the model's sensitivity.

4.  **Model Building & Comparison**: Multiple classification algorithms were trained and compared, including Logistic Regression, Decision Tree, Random Forest, XGBoost, and LightGBM.

5.  **Evaluation Metric Optimization**: Given the business importance of identifying all potential defaulters, the **F2-score** was chosen as the primary evaluation metric. This score gives more weight to recall than precision, which helps minimize costly false negatives.

6.  **Threshold Tuning**: The default probability threshold of 0.5 was tuned to optimize for the F2-score. The optimal threshold was selected based on performance on the validation set to balance predictive accuracy with business impact.

7.  **Validation & Prediction**: The final model was evaluated on a separate, unseen validation dataset to simulate real-world performance, and a prediction file was generated.

---

## 📊 Key Findings from EDA

* **Payment History is Critical**: Customers with overdue payments (`PAY_x >= 1`) in multiple past months show significantly higher default rates. Overdue payment behavior is a strong contributor to default risk.
* **Credit Utilization**: Defaulters tend to have higher credit utilization ratios, suggesting that customers spending closer to their credit limit are at greater risk.
* **Credit Limit**: The default rate decreases as the credit limit increases. Customers with lower credit limits (0-50K) have the highest default rate.
* **Age Groups**: Default rates show a tendency to increase with age, with the 60-80 age group exhibiting the highest default rates at around 30%.
* **Bill & Payment Trends**: Non-defaulters have consistently higher average monthly bill amounts, suggesting that higher spending does not necessarily lead to default if managed well. Conversely, defaulters make lower and less consistent payments, indicating irregular repayment habits.

---

## 🏆 Final Model and Performance

**Random Forest** was selected as the final model due to its superior F2-score and recall, which ensures better identification of potential defaulters.

| Model               | Accuracy | Recall | F1-Score | F2-Score |
|---------------------|----------|--------|----------|----------|
| Logistic Regression | 77.8%    | 77.9%  | 77.8%    | 77.9%    |
| Decision Tree       | 81.2%    | 74.2%  | 79.8%    | 76.3%    |
| XGBoost             | 88.4%    | 83.8%  | 87.8%    | 85.4%    |
| LightGBM            | 87.9%    | 81.9%  | 87.1%    | 83.9%    |
| **Random Forest** | **89.1%**| **85.1%**| **88.6%**| **86.5%**|


#### Classification Threshold
To better identify defaulters, the classification threshold was optimized using the F2-score. A threshold of **0.30** was selected, as it achieved the highest F2-score of **0.9033** on the validation set, making the model more sensitive to credit risk.

---

## 💼 Business Implications

* **Protects Against Loss**: The model's high recall helps minimize false negatives, reducing losses from defaults by allowing for early intervention.
* **Enables Proactive Strategy**: Early warnings allow for risk-adjusted credit limits and better financial planning.
* **Justifies Decisions**: Using behavior-based features helps justify credit actions to both customers and regulators.

---

## 📋 How to Run the Project
1.  Clone this repository to your local machine.
2.  Install the required libraries using pip:
    `pip install -r requirements.txt`
3.  Open and run the `notebook_submission__22112085.ipynb` file in a Jupyter environment.

---

## 📁 Files in This Repository
* `notebook_submission__22112085.ipynb`: The main Jupyter Notebook with all analysis and modeling code.
* `Credit_Card_Default_Report_Summary.pdf`: A summary report of the project findings.
* `train_dataset_final1.csv`: The training dataset.
* `validate_dataset_final.csv`: The validation dataset for final predictions.
* `requirements.txt`: A list of required Python libraries for reproducibility.
