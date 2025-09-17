# Predicting Batting Performance Using MLB Player Statistics
---

## 📌 Project Overview
This project explores how MLB player statistics can be used to predict batting average. Using Lahman’s Baseball Database (1871–present), we applied regression machine learning techniques to identify which statistics most strongly influence hitting performance.  

The work includes:
- Exploratory analysis of batting statistics  
- Correlation and trend identification  
- Predictive modeling with **k-Nearest Neighbors (kNN)** and **Random Forest**  
- Performance comparison across decades  

---

## 📊 Dataset
- **Source:** Sean Lahman’s Baseball Database  
- **Focus:** Batting data (player-season level)  
- **Key Features:** At-Bats (AB), Hits (H), Runs (R), Home Runs (HR), Walks (BB), Strikeouts (SO), Stolen Bases (SB), Sacrifice Hits/Flies, Plate Appearances (PA), Batting/Throwing Hand, and more  
- After cleaning and filtering (AB > 50), the dataset included **~54,000 player-seasons**  

---

## 🔍 Key Insights
- **Batting Average Distribution:** Centered between .200–.300 with few extreme outliers  
- **Correlations:**  
  - HR–SO: **0.75** (power hitters strike out more)  
  - BB–H: **0.78** (both scale with plate appearances)  
  - BA–H: **0.63** (intuitive positive link)  
- **Batting Hand Effect:** Left-handed and switch hitters generally have slightly higher averages  
- **Throwing Hand Effect:** Minimal impact on batting performance  

---

## ⚙️ Modeling
- **Preprocessing:**  
  - Removed direct BA predictors (AB, H)  
  - Encoded categorical features (team, league, batting/throwing hand)  
  - Applied transformations (log for HR/RBI, sqrt for SO)  
  - Standardized numerical features  
- **Models Tested:** k-Nearest Neighbors (kNN), Random Forest Regressor  
- **Metrics:** R² (explained variance) and RMSE (prediction error)  

---

## 📈 Results

### k-Nearest Neighbors
- Best model: **k = 9**, distance-weighted  
- Validation R²: **0.516**  
- RMSE: **0.037**  
- Performance strongest in the 1960s, weaker in later decades  

### Random Forest
- Best model: **200 trees, min_samples_leaf = 5**  
- Test R²: **0.679**  
- RMSE: **0.030** (predictions within .030 BA points)  
- More consistent and accurate than kNN across decades  

---

## 📌 Conclusions
- **Random Forest outperformed kNN**, making it the preferred model  
- Decade analysis suggests **shifts in playing styles and league conditions** affect predictability  
- Batting average remains difficult to predict due to missing contextual factors (pitcher matchups, ballpark effects, injuries, etc.)  

---

## 🚀 Future Work
- Incorporate **pitching stats** (ERA, WHIP, pitch type)  
- Add **contextual features** (ballpark, weather, home/away splits)  
- Use **advanced metrics** (xBA, OPS, wOBA, WAR)  
- Explore **ensemble models and deep learning**  

---
