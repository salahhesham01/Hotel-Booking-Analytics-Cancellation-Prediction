#  Hotel Booking Analytics & Cancellation Prediction

A complete end-to-end data science project covering exploratory analysis, business intelligence dashboards, and machine learning — built on a real-world hotel reservations dataset.

---

##  Project Overview

This project analyzes hotel booking data to understand cancellation behaviour, pricing patterns, seasonality, customer profiles, and market segments. It then builds a machine learning model to predict whether a booking will be cancelled.

**The project has 3 layers:**
- **Power BI Dashboard** — 5-page interactive business intelligence report
- **Business Report** — written insights and recommendations for stakeholders
- **ML Model** — XGBoost cancellation prediction model with SHAP explainability

---

##  Dashboard Preview

### Cancellation Analysis
<img width="1236" height="677" alt="image" src="https://github.com/user-attachments/assets/c7a13927-ec7e-48cb-ae6b-52cc60ec957a" />

### Pricing Analysis
<img width="1238" height="681" alt="image" src="https://github.com/user-attachments/assets/435b31e3-0bf7-49bf-a35e-1e7ec3bc2092" />


### Seasonality Analysis
<img width="1236" height="675" alt="image" src="https://github.com/user-attachments/assets/7d8a2800-0a4a-4345-87d6-3f368b5338da" />


### Customer Analysis
<img width="1238" height="677" alt="image" src="https://github.com/user-attachments/assets/34c539b9-4f2d-459f-9464-d73d2c804eb1" />


### Market Analysis
<img width="1239" height="673" alt="image" src="https://github.com/user-attachments/assets/d132004d-135f-4b8e-b079-a806ab969b76" />


---

##  Key Business Metrics

| Metric | Value |
|---|---|
| Total Bookings | 36,000 |
| Cancellation Rate | 32.76% |
| Total Revenue | $2.44M |
| Average Daily Rate | $99.93 |
| Potential Revenue Loss | $1.31M |
| Avg. Length of Stay | 3.02 nights |
| Repeated Guest Rate | 2.56% |

---

##  Key Insights

- **Lead time** is the strongest cancellation driver — bookings made 350+ days ahead cancel at 100%
- **Repeated guests** cancel at only 1.72% vs 33.58% for new guests — a 19x difference
- **Special requests** dramatically reduce cancellation — 0 requests = 43% cancel rate, 3+ requests = 0%
- **Online channel** has the highest cancellation rate (36.51%) but generates the most revenue ($2.61M)
- **Corporate segment** is the most reliable — only 10.94% cancellation rate
- **July** is the most volatile month — highest cancellation rate at 45% despite peak ADR

---

##  Machine Learning Model

### Goal
Predict whether a hotel booking will be cancelled (binary classification).

### Models Compared

| Model | Accuracy | Precision | Recall | F1 Score | AUC-ROC |
|---|---|---|---|---|---|
| Logistic Regression | 80.43% | 70.46% | 55.08% | 61.83% | 0.8470 |
| Random Forest | 84.96% | 77.12% | 67.88% | 72.21% | 0.8992 |
| **XGBoost** ✅ | **85.47%** | **78.91%** | **67.54%** | **72.79%** | **0.9135** |

**XGBoost** was selected as the final model with **91.35% AUC-ROC**.

### ML Results

#### Confusion Matrices
<img width="1693" height="495" alt="image" src="https://github.com/user-attachments/assets/027a9584-dcad-4061-96bd-92a3b6cdaf77" />


#### ROC Curve
<img width="790" height="590" alt="image" src="https://github.com/user-attachments/assets/5aff5960-98d8-4428-b090-b03e28c79510" />


#### XGBoost Feature Importance
<img width="990" height="690" alt="image" src="https://github.com/user-attachments/assets/5847392d-085a-46ca-929c-339b7200332b" />


### SHAP Explainability

SHAP (SHapley Additive exPlanations) was used to explain the model's predictions — showing not just *what* the model predicted but *why*.

#### SHAP Feature Importance (Bar)
<img width="790" height="740" alt="image" src="https://github.com/user-attachments/assets/80366aa8-983e-41f6-a307-d5568357eb8f" />

#### SHAP Summary Plot
<img width="791" height="740" alt="image" src="https://github.com/user-attachments/assets/a6ab748e-73b0-4290-9edf-804abecede54" />


### Top Cancellation Drivers (SHAP)

| Rank | Feature | Effect |
|---|---|---|
| 1 | `lead_time` | Higher lead time → higher cancellation probability |
| 2 | `no_of_special_requests` | More requests → lower cancellation probability |
| 3 | `market_segment_type` | Online segment → higher cancellation risk |
| 4 | `avg_price_per_room` | Higher price → higher cancellation probability |
| 5 | `arrival_month` | Summer months → higher cancellation risk |

> **Note:** SHAP rankings differ from XGBoost's built-in feature importance. SHAP is more trustworthy because it measures the actual impact on each individual prediction rather than just counting how often a feature was used in tree splits.



---

##  Tools & Technologies

| Category | Tools |
|---|---|
| Dashboard & BI | Power BI, DAX |
| Data Modeling | Star Schema (Fact + Dimension tables) |
| Programming | Python |
| ML Libraries | scikit-learn, XGBoost, SHAP |
| Data Processing | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Environment | Google Colab |
| Version Control | Git, GitHub |



##  Dataset

- **Source:** Hotel Reservations dataset
- **Original size:** 36,275 rows × 19 columns
- **After cleaning:** 33,798 rows × 16 features
- **Target variable:** `booking_status` (Canceled / Not_Canceled)
- **Class balance:** 71.1% Not Canceled | 28.9% Canceled

---

##  Business Recommendations

1. **Introduce deposit policies** for bookings with lead time > 90 days
2. **Build a loyalty programme** — repeated guests cancel 19x less than new guests
3. **Encourage special requests** at booking time to increase guest commitment
4. **Redesign Meal Plan 2** — it has the highest cancellation rate at 45.57%
5. **Expand corporate channel** — lowest cancellation rate at 10.94%
6. **Implement dynamic pricing** for summer months where cancellation peaks at 45%

---

##  Author

**Salah Alaskary**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)]([https://linkedin.com/in/yourprofile](https://www.linkedin.com/in/salah-hesham/))

