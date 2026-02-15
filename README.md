# Why Subscription Metadata Fails to Predict Churn  
### A Product Analytics Investigation

## 📌 Business Question

Can subscription-level commercial metadata (plan tier, billing frequency, seats, MRR, renewals, upgrades/downgrades) effectively predict customer churn?

---

## 🎯 Hypothesis

If churn is primarily driven by engagement and value realization rather than pricing configuration, then commercial subscription metadata alone should have limited predictive power.

---

## 🗂 Dataset

The analysis uses three structured datasets:

- **Subscriptions** – plan tier, billing frequency, seats, MRR, trial status, churn flag
- **Churn Events** – churn date and reason codes
- **Feature Usage** – event-level feature interactions per subscription

---

## 🔎 Exploratory Analysis

### 1️⃣ Lifecycle Distribution
Subscriptions were segmented into:
- Trial
- Active
- Churned

Tenure analysis showed predictable lifecycle separation, but no strong commercial signal distinguishing early churners.

---

### 2️⃣ Churn Timing

Churn events were categorized into:
- Early churn (0–7 days)
- Mid churn (8–30 days)
- Late churn (30+ days)

Plan tiers did not meaningfully differentiate early churn patterns.

---

### 3️⃣ Early & Ultra-Early Churners (0–7 Days)

Key finding:

Commercial features such as:
- Seats
- MRR
- Plan tier
- Billing frequency
- Upgrade/downgrade flags
- Auto-renew status  

did **not** strongly differentiate ultra-early churners from retained users.

This suggests churn at this stage is likely behavioral rather than commercial.

---

## 🤖 Predictive Modeling

A baseline Logistic Regression model was trained using only subscription-level commercial metadata.

**Features used:**
- Seats
- MRR
- Trial status
- Upgrade flag
- Downgrade flag
- Auto-renew flag
- Plan tier (encoded)
- Billing frequency (encoded)

### 📊 Result

An AUC close to 0.50 indicates performance near random guessing.

### 🔎 Conclusion from Modeling

ubscription-level commercial metadata does **not** meaningfully differentiate churn risk in this dataset.

This suggests churn behavior is likely driven by activation and engagement dynamics rather than pricing configuration or billing attributes.

---

## 📊 Interactive Dashboard (Count)

An executive-facing dashboard was built in **Count** to visualize:

- Churn timing distribution by plan tier  
- Early churn comparisons across commercial features  
- Distribution overlap in MRR and seats  
- High-level churn KPIs  

👉 **View the interactive dashboard here:**  
[Count Dashboard – Public Link](https://app.count.co/canvas/ETYO0D78PhN)

---

## 🧠 Strategic Takeaway

Churn prediction cannot rely on pricing metadata alone.  
Signal likely resides in activation milestones and behavioral engagement metrics.

Recommended tracking improvements:

- Login frequency
- Time to first meaningful action
- Feature adoption depth
- Session duration
- Trial milestone completion
- Activation event tracking

---

## 🛠 Tech Stack

- Python
- Pandas / NumPy
- Seaborn / Matplotlib
- Scikit-learn
- Count (BI dashboard)


---

## 📌 Key Insight

You cannot predict churn using pricing knobs if churn is caused by customers never realizing value.

