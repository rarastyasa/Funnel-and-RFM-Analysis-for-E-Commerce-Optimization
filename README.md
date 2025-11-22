# 📘 Funnel & RFM Analysis — E-Commerce Customer Insights

This project provides a complete analytical workflow to understand customer purchasing behavior using **Sales Funnel Analysis** and **RFM (Recency–Frequency–Monetary) Segmentation**.  
It covers data cleaning, feature engineering, funnel performance evaluation, customer scoring, and RFM-based segmentation to support **data-driven decision making** for e-commerce businesses.

---

## 1️⃣ Business Understanding

The goal of this project is to help the business:

- Measure efficiency of the sales funnel
- Identify where customers drop off
- Segment customers based on buying behavior
- Improve marketing personalization and retention strategies

**Key Business Questions:**

1. Funnel Analysis Questions

* How many users are present at each stage of the funnel (view → add_to_cart → checkout → purchase)?

* What are the conversion rates between each stage, and where does the largest drop-off occur?

2. RFM Analysis Questions

* How are customers segmented based on their RFM scores?

* Which customer segments contribute the most to total sales?

* What marketing strategies are suitable for each customer segment?

---

## 2️⃣ Data Understanding

The dataset contains customer behaviour data for e-commerce with the following key fields:

| **Column Name** | **Description** |
|------------------|-----------------|
| **User_ID** | Unique identifier for each user. |
| **Session_ID** | Unique session identifier for tracking individual user sessions. |
| **DateTime** | Timestamp of the interaction. |
| **Category** | Product category being viewed or interacted with. |
| **SubCategory** | Detailed subcategory within the main product category. |
| **Action** | Type of user action (e.g., search, view product, add to cart, etc.). |
| **Quantity** | Number of items in a transaction (if applicable). |
| **Rate** | Price rate of the product (if applicable). |
| **Total Price** | Total transaction amount (if applicable). |

**Data exploration includes:**

- Missing value analysis  
- Outlier detection  
- Duplicate removal  
- Basic descriptive statistics

#### Dataset Source: https://www.kaggle.com/datasets/adithiav/e-commerce-customer-behavior-data
---

## 3️⃣ Data Preparation

**✔ Cleaning:**

- Changing Data Types  
- Removed Missing value     
- Removed outlier in RFM Dataset  

**✔ Making Funnel and RFM Dataset:**

- Funnel: Actions used by first_open_up, product_view, add_to_cart, checkout, and purchase  
- RFM : Only includes users and events leading up to the “purchase” action.  

---

## 4️⃣ Funnel Analysis

The sales funnel is evaluated across key stages such as:

- first_open_up  
- product_view  
- add_to_cart  
- purchase
- 

**Includes:**

- Customer counts per funnel stage  
- Stage-to-stage conversion rates  
- Drop-off analysis  
- Funnel visualization  
- Category-level conversion comparison  

*These metrics help identify which stages need optimization.*

---

## 5️⃣ RFM Analysis

RFM is calculated using:

- **Recency (R):** Days since last purchase  
- **Frequency (F):** Number of transactions  
- **Monetary (M):** Total spending  

**Steps:**

1. Calculating R, F, M values  
2. Computing quantile cutoffs  
3. Assigning RFM scores (1–5)  
4. Generating a combined `RFM_Score`  

**Example:** `544` means  
- R = 5 (very recent)  
- F = 4 (frequent)  
- M = 4 (high spending)  

---

## 6️⃣ Customer Segmentation

Based on RFM scoring, customers are segmented using the following rules:

| Segment            | R Condition | F Condition | M Condition | Description |
|-------------------|-------------|------------|-------------|-------------|
| Champion           | R = 5       | F ≥ 4      | M ≥ 4       | Best customers: recent, frequent, high-value buyers |
| Loyal Customer     | R ≥ 4       | F ≥ 4      | —           | Repeat buyers with strong loyalty |
| Potential Loyalist | R ≥ 4       | F ≥ 3      | —           | Close to becoming loyal; repeat pattern emerging |
| Recent Customer    | R = 5       | —          | —           | Recently purchased; onboarding opportunity |
| Promising          | R ≥ 3       | F ≥ 2      | —           | Growing activity and potential |
| Needs Attention    | R ≥ 2       | F ≥ 1      | —           | Declining engagement; needs reactivation |
| At Risk            | else        | —          | —           | Long inactive; high churn risk |

*These segments support targeted marketing strategies.*

---

## 7️⃣ Insights & Recommendations

1. Enhance Product Pages

* Improve product visuals and descriptions.

* Highlight key benefits to reduce drop-off from Product View → Add to Cart.

* Display shipping estimates early, enable “Buy Now,” and send cart reminders.

2. Leverage Engagement Features

* Encourage customers to write reviews.

* Use wishlist data for targeted promotions and price-drop alerts.

3. Use RFM Insights for Targeted Marketing

* Promote Promising users into Loyal/Champion via personalized deals.

* Re-engage At Risk & Needs Attention customers with win-back offers.

* Reward Champions & Loyal buyers with exclusive benefits to increase retention.
