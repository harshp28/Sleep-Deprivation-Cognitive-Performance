
# **Sleep Deprivation & Cognitive Performance: Machine Learning Analysis**

## **Objective**  
The goal of this project was to analyze the **impact of sleep deprivation on cognitive performance** (measured by *Stroop Task Reaction Time*) using machine learning models.  

---

## **Dataset Overview**  
The dataset included sleep-related, stress-related, and cognitive performance metrics. Key features used in model training:  

- **Sleep Factors:** `Sleep_Debt`, `Sleep_Variability`, `REM_Sleep_Estimate`  
- **Caffeine & Stress Interactions:** `Caffeine_Sensitivity`, `Stress_Caffeine_Interaction`  
- **Exercise & Alertness:** `Exercise_Stress_Buffer`, `Alertness_Score`  

These features were selected based on **feature importance analysis**.

---

## **Exploratory Data Analysis (EDA) Findings**
- **Correlation Analysis:**  
   - Higher `Sleep_Debt` and `Sleep_Variability` were linked to worse cognitive performance.  
   - `Exercise_Stress_Buffer` had a weak positive impact on reaction time.  

- **Data Preprocessing & Feature Engineering:**  
   - Standardized numerical features.  
   - Selected **top 7 features** for modeling.  
   - Explored **ensemble learning** to improve predictions.  

---

## **Model Performance Summary**  

| **Model**                 | **R² Score** | **MAE**  | **RMSE**  |
|---------------------------|------------|----------|----------|
| **LightGBM Meta-Learner** *(Optimized)* | **-0.0926**  | **0.7345**  | **0.8767**  |
| LightGBM (Feature Selected) | -0.1113  | 0.7398  | 0.8841  |
| XGBoost | -0.3401  | 0.8379  | 0.9709  |
| Random Forest | -0.1390  | 0.7718  | 0.8951  |
| CatBoost Meta-Learner | -0.4063  | 0.8487  | 0.9946  |
| Neural Network (MLP) | -2.7074  | 1.3575  | 1.6149  |
| **Stacked Ensemble (LightGBM Meta-Learner)** | **0.0613**  | **0.5932**  | **0.8126**  |
| Tuned Stacked Ensemble (XGBoost) | -0.0478  | 0.6912  | 0.8585  |

- **Best Model:** Stacked Ensemble (LightGBM Meta-Learner)  
- **Lowest MAE & RMSE:** Shows best predictive accuracy.  
- **Neural Network & CatBoost Performed Poorly:** Likely due to limited dataset size and feature availability.  

---

## **Key Takeaways**
- **Feature Selection Helped:** Using only **7 key features** improved model efficiency.  
- **Ensemble Learning Worked Best:** Stacked models performed better than individual models.  
- **LightGBM Outperformed Others:** Best balance of speed and accuracy.  
- **Dataset May Need More Inputs:** **Missing physiological or behavioral factors** could explain why models struggle to predict reaction time.  

---

## **Next Steps for Future Work**
- **Expand Dataset with More Features** (e.g., heart rate, sleep quality metrics, previous reaction time history).  
- **Consider Temporal Models (LSTMs, Transformers)** for sequential sleep patterns.  
- **Optimize Meta-Learners with Hyperparameter Tuning** for better performance.  
- **Blend LightGBM & Neural Networks** to capture both structured & deep patterns.  

---

### **Final Conclusion**
**LightGBM-based stacked ensemble provided the best results** for predicting cognitive performance under sleep deprivation. However, further **data collection and feature expansion** is required to achieve higher accuracy.  
