# Predicting Company Default Risk Using Corporate Transaction Graphs

This project explores how financial transaction networks can reveal structural patterns of risky company behavior (e.g., money laundering) using synthetic data from IBM AMLSim.

---

## 🔍 Project Goals
- Construct company-level graphs from transactions
- Label risky entities based on laundering behavior
- Extract structural graph features (degree, PageRank, centralities)
- Train models to predict default risk
- Evaluate performance and impact of class imbalance

---

## 📁 Repo Structure
- `data/`: HI-Small dataset (CSV + laundering patterns)
- `notebooks/`: Python notebooks for graph construction, EDA, modeling
- `reports/`: CP1 + CP2 reports in PDF and markdown
- `requirements.txt`: Dependencies for running the project

---

## 📊 Dataset Summary
- **Source**: IBM AMLSim HI-Small Dataset  
  [Kaggle link](https://www.kaggle.com/datasets/ealtman2019/ibm-transactions-for-anti-money-laundering-aml)
- **Type**: Synthetic financial transactions among companies, individuals, and banks
- **Nodes**: 514,210 accounts
- **Edges**: 989,036 directed transactions
- **Labeling**: Involvement in laundering patterns → `defaulted = 1`

---

## 📈 EDA & Graph Analysis
- Graph is highly sparse (density ~ 0.0000037), many weakly connected components
- Most nodes have low degree; few hubs exhibit high centrality
- Defaulted entities are structurally subtle (not outliers)
- Target imbalance: only ~0.9% of nodes are labeled as defaulted

---

## 🧪 Modeling and Results
- **Baseline**: Random Forest with balanced class weights  
  - Accuracy: 98.1%  
  - Recall for defaults: 3.4% (low sensitivity)

- **With SMOTE Oversampling**:  
  - Recall: ↑ to 50.5%  
  - Precision: ↓ to 2.1%  
  - Accuracy: ↓ to 75.7%  
  - Strong tradeoff between detecting rare cases and false positives

---

## 🧠 Key Takeaways
- Graph-based features alone are not enough for high-precision fraud/default detection
- SMOTE helps sensitivity but requires better control of false positives
- Next steps (CP3): advanced graph models (GNNs, community detection), time-aware edges

---

## 📌 CP2 Status
✅ Project Repository created  
✅ Data loaded and graphed  
✅ Feature extraction & imbalance handling  
✅ Modeling + Evaluation with and without SMOTE  
✅ CP2 Presentation: `/reports/CP2_Presentation.pdf`

---

## 👤 Authors
**Sanjar Javodov**  
**Kahorov Payrav**
