# 📺 StreamZone TV: Predicting Freemium-to-Paid Conversion


## Business Case
- **Context:** A "Freemium" streaming app (Live TV + Replay).
- **Problem:** The marketing team needs to identify which free users are most likely to convert to paid.
- **Solution:** A Random Forest classifier that scores users based on behavioral signals (Watch Time, Device Type, Replay usage).
- **Product Action:** The model outputs a propensity_score which triggers specific user flows:
      1. High Intent (> 70%): Show immediate "Premium" checkout prompt.
      2. Medium Intent (40-70%): Send a targeted 10% discount notification.
      3. Low Intent (< 40%): No action (focus on Ad revenue).

## Tech Stack
- **Core Logic:** Python, Scikit-Learn
- **Data Processing: Polars** (Used for high performance data manipulation)
- **Visualization:** Plotly Express (Interactive EDA)
- **Deployment:** Joblib (Model serialization for production)

## Key Components
1. **Synthetic Data Generation:**
    - Simulated a realistic dataset of 10000 users.
    - Modeled specific behaviors (e.g. Smart TV users have higher retention than Mobile users).

2. **Exploratory Data Analysis (EDA):**
    - Used Plotly to visualize the 'North Star Metric': the correlation between weekly_watch_hours and conversion probability

3. **ML Pipeline:**
     - Implemented a scikit-learn Pipeline with ColumnTransformer and OneHotEncoding.
     - Trained a RandomForestClassifier to handle non-linear relationships

4. **Batch Inference System:**
     - Created a production-ready function run_batch_prediction() that:
          - Ingests raw CSV user logs via **Polars**
          - Loads the trained model via **Joblib**.
          - Outputs a filtered list of 'High Value Targets' for marketing campaigns
      
  ## Results
  - Built a reproducible pipeline that bridges the gap between Data Science (Training) and Engineering (Deployment)
  - Demonstrated how to use **Polars** for efficient feature engineering in a production context.


## Previews

**Conversion Rate by Device**
<img width="1724" height="525" alt="conversion rate by device" src="https://github.com/user-attachments/assets/3179c048-61e2-4b64-b93e-1bd2fbb870c2" />


**High Value Users**
<img width="1724" height="525" alt="high value users" src="https://github.com/user-attachments/assets/eade35d2-f579-46ff-ac10-c0d6bc0c47cf" />


    
