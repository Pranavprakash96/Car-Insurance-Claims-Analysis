📘 Insurance Claim Cost Modeling with XGBoost

🔍 Project Overview

This project aims to build and interpret an XGBoost regression model to predict insurance claim cost (CLM_AMT) using various policyholder and vehicle-related features. The focus is on extracting actionable insights for pricing and risk segmentation purposes in the insurance domain.

🎯 Objective

Predict expected claim amount (risk cost) for each policy

Generate relativity factors to support pricing decisions

Evaluate model performance using insurance-relevant metrics (Gini index, decile lift)

Interpret model outputs using SHAP for pricing transparency

🗃️ Dataset

Target Variable:

CLM_AMT: Actual claim amount

Key Features Used:

Demographics: AGE, HOMEKIDS, YOJ, INCOME, GENDER, EDUCATION

Vehicle: CAR_TYPE, CAR_AGE, RED_CAR, BLUEBOOK

Behavior: MVR_PTS, TRAVTIME, TIF, CLM_FREQ, REVOKED

Address/Policy: HOME_VAL, URBANICITY, PARENT1, MSTATUS, OCCUPATION

Note: Categorical variables are label encoded for model compatibility.

⚙️ Model Training

Model Used: XGBRegressor

Parameters: max_depth=4, learning_rate=0.1, n_estimators=100, subsample=0.8

Encoding: LabelEncoder for categorical features

Evaluation Split: 80% Train / 20% Test

📈 Evaluation Metrics

Predicted Claim Cost: Core output from XGBoost

Relativity: Ratio of each prediction to the portfolio average

Decile Lift Chart: Shows how well the model segments high vs low risk

Normalized Gini Index: Measures the model's rank-order performance

🔍 Model Interpretation

SHAP (SHapley Additive Explanations)

Explains which features increased or decreased the prediction for each policy

Helps bridge the gap between machine learning and actuarial fairness

Visuals: SHAP summary bar plot, waterfall plot per policy

📊 Use in Pricing

Relativities can be binned into pricing tiers (e.g., 0.8x, 1.0x, 1.2x)

SHAP helps validate feature influence (e.g., "Is 'CAR_TYPE' or 'URBANICITY' driving higher premiums?")

Gini index and decile charts help assess business value and ranking ability

🛠️ Future Enhancements

Try Tweedie loss for compound Poisson-gamma distribution

Incorporate GLM for comparison

Explore calibration or blending with business rules

Create pricing dashboards in Power BI or Tableau

📂 Files

car_insurance_claim.csv: Raw input data

XGB_model.ipynb or equivalent: Model training and interpretation

👨‍💼 Author

This project was developed as part of a data science workflow for insurance pricing model exploration using XGBoost.

📬 Questions?

Reach out if you’d like help packaging this into a presentation or sharing it with pricing/actuarial teams!
