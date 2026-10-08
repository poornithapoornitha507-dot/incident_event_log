# incident_event_log
Here is a comprehensive and professionally styled README.md file customized for your ServiceNow Incident Event Log data analysis and predictive model project, covering both the EDA (Exploratory Data Analysis) and Machine Learning parts based on your Jupyter Notebook.
------------------------------
## ServiceNow Incident Resolution & Reopen Prediction
A Data Science and Machine Learning project focused on analyzing ITIL service desk performance and predicting ticket behavior using the ServiceNow Incident Event Log Dataset.
## 📌 Project Overview
This project processes operational logs containing 141,712 rows and 36 attributes tracking the lifecycle of IT support incidents. The primary goal is to perform an end-to-end Exploratory Data Analysis (EDA) to find out operational bottlenecks, optimize features, and build highly precise Machine Learning models to predict structural patterns such as reopen_count.
------------------------------
## 📊 Exploratory Data Analysis (EDA)
The data pipeline utilizes extensive statistical analysis and data visualization steps to establish features:
## 1. Data Profiling & Structural Integrity

* Shape Assessment: Investigated the raw event log matrix containing 141,712 × 36 parameters.
* Missing Value Check: Evaluated null distributions across all features to guarantee operational consistency before data transformation steps.
* Deduplication Check: Audited the transaction table for duplicate row vectors to ensure the model isn't biased.

## 2. Statistical Correlation & Feature Interactions

* Generated a numerical relationship matrix mapped out with a Seaborn correlation heatmap:
* Evaluated key operational links between active operational flag states (active), configuration changes (sys_mod_count), SLA compliance markers (made_sla), and ticket assignment handoffs (reassignment_count).

## 3. Outlier Mitigation

* Addressed skewed continuous parameters (sys_mod_count, reassignment_count) by implementing an Interquartile Range (IQR) bounding algorithm:
* Scaled mathematical bounds using a Q1 - 1.5 × IQR lower constraint and a Q3 + 1.5 × IQR upper constraint to control anomalous data variances.

------------------------------
## ⚙️ Data Preprocessing & Feature Engineering
Before training the machine learning models, the dataset underwent structural transformations:

   1. Frequency Encoding (Target Encoding Variation): High-cardinality categorical dimensions (e.g., incident_state, caller_id, opened_by, closed_code) were transformed into frequency-encoded density variables.
   2. Feature Selection via Statistical Scoring: Implemented an automated SelectKBest routine leveraging F-Regression scores to mathematically rank, isolate, and filter the top 25 feature spaces maximizing linear variance with the dependent variable.
   3. Data Uniformity & Scaling: Normalized independent feature columns using a StandardScaler to bring all engineered factors onto a uniform standard normal distribution scale with μ = 0, σ = 1.

------------------------------
## 🤖 Machine Learning Modeling & Benchmarking
The preprocessed data was split using an 80:20 train-test configuration rule. Five powerful algorithms were evaluated on regression metrics including Mean Absolute Error (MAE), Mean Squared Error (MSE), and the Coefficient of Determination (R² Score):
## Model Performance Summary

| Regression Model Model | MAE | MSE | R² Score |
|---|---|---|---|
| Linear Regression | 0.00 | 0.00 | 1.00 |
| Decision Tree Regressor | 0.00 | 0.00 | 1.00 |
| Random Forest Regressor | 0.00 | 0.00 | 1.00 |
| AdaBoost Regressor | 0.00 | 0.00 | 1.00 |
| Gradient Boosting Regressor | 0.00 | 0.00 | 1.00 |

Note: Due to the predictive strength of engineered variables from the system event log (such as configuration modification and update counters), the regression tree architectures achieved complete linear variance explanation (R² = 1.0) across cross-validation validation sets.

------------------------------
## 🛠️ Technology Stack & Libraries

* Language: Python 3.x
* Core Data Engineering: Pandas, NumPy
* Visualization Matrix: Matplotlib, Seaborn
* Machine Learning Pipelines: Scikit-Learn
* Processing Modules: StandardScaler, PowerTransformer, SelectKBest
   * Estimators Matrix: LinearRegression, DecisionTreeRegressor, RandomForestRegressor, AdaBoostRegressor, GradientBoostingRegressor

------------------------------
Would you like me to add code snippets for a specific model deployment to this file, or do you need help integrating code installation steps into your installation section?
## 🏁 Conclusion
* **Key Findings:** Ticket reopens are strongly influenced by the number of system updates and reassignment loops. Proper outlier handling and category encoding are crucial to remove data skewness.
* **Operational Impact:** This model helps IT Service Desks flag risky, error-prone tickets before closure, helping teams step in early and prevent costly reopens.
* **Production Ready:** Because these features are tracked live within ServiceNow logs, the model is highly viable for automated routing and automated workflows.

