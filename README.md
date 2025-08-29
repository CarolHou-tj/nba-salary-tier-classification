## 📌 Project Overview

This project explores the relationship between **NBA player
performance** and their **salary tiers** using data from the 2022-23
season.  
Instead of predicting exact salary amounts, we grouped players into
salary ranges (Budget, Mid-Tier, Upper Mid-Tier, Premium).  
We built and compared multiple machine learning models to evaluate their
ability to classify players into the correct salary tier.

**Key Objectives:** - Predict salary groups rather than exact amounts to
reduce the impact of outliers.  
- Help teams, scouts, and agents assess relative player value for
strategic decisions.  
- Apply multiple classification methods and identify the best-performing
model.

------------------------------------------------------------------------

## 📊 Dataset

-   **Source:** [Kaggle NBA Player Salaries 2022-23
    Season](https://www.kaggle.com/datasets/jamiewelsh2/nba-player-salaries-2022-23-season?select=nba_salaries.csv)  
-   **Entries:** 467 players  
-   **Selected Features:**
    -   Assists (AST)  
    -   Steals (STL)  
    -   Blocks (BLK)  
    -   Turnovers (TOV)  
    -   Personal Fouls (PF)  
    -   Points (PTS)  
    -   Salary Group (target variable)

**Salary Groups:** 
- **Budget Tier:** Bottom 25%  
- **Mid-Tier:** 25%–50%  
- **Upper Mid-Tier:** 50%–75%  
- **Premium Tier:** Top 25%

**Data Split:** Stratified sampling with `createDataPartition()` to
preserve class distribution across training/testing sets.

------------------------------------------------------------------------

## ⚙️ Models Applied

We evaluated the following models with **cross-validation and parameter
tuning**:

<table>
<colgroup>
<col style="width: 51%" />
<col style="width: 20%" />
<col style="width: 28%" />
</colgroup>
<thead>
<tr>
<th>Model</th>
<th>Accuracy</th>
<th>Key Findings</th>
</tr>
</thead>
<tbody>
<tr>
<td>Logistic Regression</td>
<td>41.3%</td>
<td>Assists negatively correlated with higher salary groups; points and
blocks strong predictors of Premium.</td>
</tr>
<tr>
<td>LDA</td>
<td>45.65%</td>
<td>Better for extreme groups (Budget &amp; Premium), struggles with
overlapping mid-range classes.</td>
</tr>
<tr>
<td>QDA</td>
<td>47.1%</td>
<td>Flexible but prone to overfitting; poor at mid-range
classification.</td>
</tr>
<tr>
<td>KNN (k=11)</td>
<td>45.7%</td>
<td>Captures non-linear relationships, but misclassifies Mid &amp; Upper
Mid Tiers.</td>
</tr>
<tr>
<td>Decision Trees (size=6)</td>
<td><strong>55.03%</strong></td>
<td>Best performance; key splits on points, fouls, and assists; risk of
overfitting.</td>
</tr>
<tr>
<td>SVM (radial, C=1, γ=0.5)</td>
<td>50.67%</td>
<td>Poor sensitivity for mid-tier groups.</td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------

## 🏆 Results

-   **Decision Trees** performed the best with ~55% accuracy.  
-   Most models struggled with **Mid-Tier and Upper Mid-Tier groups**
    due to feature overlap.  
-   **Points** and **assists** consistently emerged as strong predictors
    across models.

------------------------------------------------------------------------

## 👤 Author

-   **Te-Jou Hou** —
    [LinkedIn](www.linkedin.com/in/te-jou-hou) ·
    [Email](mailto:th5955a@american.edu)

-   **Sean Hsu**

-   **Chih-Chen Wang**

-   **Fang-Yi Wu**
