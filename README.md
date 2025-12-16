**Predicting Click-Through Rate (CTR) for Digital Advertising**

**Columbia University - Applied Machine Learning I**  
**Final Project Score: 145/150 (96.7%)**

---

**Project Overview**

Click-through rate (CTR) is a critical metric for digital advertising platforms like Google Ads, Meta Ads, and e-commerce sites. 
This project developed a machine learning model to predict CTR for online advertisements, achieving an **RMSE of 0.07524** on the private leaderboard.

**Business Context**
Accurate CTR prediction enables:
- **Optimized ad targeting** and bidding strategies
- **Maximized ROI** for advertisers  
- **Improved user experience** through more relevant ads

**Key Achievement**
Successfully predicted ad click behavior across 1,000 test advertisements in competitive class setting.

---

**Technical Approach**

**Dataset**
- **Training data:** 4,000 observations with 29 variables
- **Test data:** 1,000 observations  
- **Target variable:** CTR (click-through rate percentage)
- **Challenge:** Significant missing data (up to 237 missing values per variable)

**Methodology**

**1. Data Preprocessing**
- **Missing value imputation:** Tested multiple strategies (median/mode, MICE, vtreat)
- **Feature engineering:** Created polynomial features for key predictors
- **Data transformation:** Log transformation for CTR in linear models
- **Standardization:** Applied for linear regression models

**2. Feature Selection**
Multiple techniques explored:
- Correlation-based filtering (final approach)
- Stepwise regression (forward, backward, both directions)
- AIC/BIC criterion selection  
- Subset selection with regsubsets

**Key predictors identified:**
- `visual_appeal` (strongest predictor)
- `targeting_score`
- `headline_length`  
- `cta_strength`
- `ad_format` (Video)
- `location` (Northeast)
- `time_of_day` (Morning)

**3. Models Tested**
- Linear Regression (with polynomial features)
- Lasso & Ridge Regression  
- Regression Trees (tuned)
- Random Forest (tuned)
- **XGBoost** (final model) 

**4. Model Optimization**
- Hyperparameter tuning via cross-validation
- Early stopping to prevent overfitting
- Optimal rounds selection (cv$best_iteration)

---

**Results**

**Final Model Performance (XGBoost with vtreat)**

| Metric | Score |
|--------|-------|
| **Private Leaderboard RMSE** | **0.07524** |
| Train RMSE | 0.07596 |
| Test RMSE | 0.07214 |
| CV RMSE | ~0.072 |

**Model Configuration**
```r
XGBoost parameters:
- eta (learning rate): 0.1
- max_depth: 4
- min_child_weight: 3
- subsample: 0.6
- colsample_bytree: 0.6
- lambda (L2 regularization): 1
- alpha (L1 regularization): 1
```

**Academic Evaluation**
- **Quality of Modeling:** 70/75
- **Quality of Investigation:** 25/25 
- **Quality of Writing:** 25/25 
- **Total Score:** 145/150 (96.7%)

**Professor Feedback:**
> "The investigation process was well thought out and included insight reflections. The student investigated the interplay between data cleaning, preprocessing, feature engineering, and feature selection processes. The code was straight-forward and contained good commentary."

---

**Key Learnings**

1. **Feature selection is critical** - Different methods yield different results; testing multiple approaches is essential

2. **Overfitting prevention requires multiple strategies:**
   - Cross-validation
   - Hyperparameter tuning
   - Early stopping
   - Regularization (L1/L2)

3. **Model-specific preprocessing matters:**
   - Standardization improved linear models but wasn't needed for tree-based models
   - Log transformation helped linear models but hurt XGBoost performance

4. **Domain knowledge complements data science:**
   - Research on CTR drivers (headline importance, device type, ad format) informed feature selection
   - Theory-guided variable selection improved model interpretability

5. **XGBoost excels at automated feature selection** - Manual feature selection didn't improve XGBoost (unlike simpler models)

---

## Technologies Used

**Languages & Tools:**
- R (primary language)
- RStudio (development environment)

**Key Libraries:**
- `xgboost` - Gradient boosting implementation
- `caret` - Machine learning workflow & cross-validation
- `vtreat` - Advanced data preprocessing
- `MASS` - Stepwise regression (stepAIC)
- `leaps` - Subset selection (regsubsets)
- `skimr` - Data exploration

**Techniques:**
- Supervised Learning (Regression)
- Hyperparameter Tuning
- Cross-Validation
- Feature Engineering
- Missing Data Imputation

---

## Repository Contents

- `Alessia_Laziosi_-_PAC_project.qmd` - Complete analysis report (Quarto document)
- `Alessia_Laziosi_-_PAC_project.html` - Rendered HTML report
- `Alessia_Laziosi_PAC-competition-Presentation.html` - Project presentation

---

## Course Information

**Institution:** Columbia University  
**Program:** MS in Applied Analytics  
**Course:** Applied Machine Learning I  
**Semester:** Spring 2025  
**Instructor:** Mark Kinsky

---

## Connect

**LinkedIn:** [linkedin.com/in/alessialaziosi](https://www.linkedin.com/in/alessialaziosi/)  
**Email:** al4840@columbia.edu

---

## License

This project was completed as part of academic coursework at Columbia University. The code and analysis are shared for educational and portfolio purposes.

---

## Acknowledgments

Special thanks to Professor for designing this challenging and educational competition, and to my Columbia classmates for the collaborative learning environment.

---

*Last updated: December 2025*
