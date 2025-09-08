# Genetic Prediction Model for Early-Onset POAG using Whole-Exome Sequencing and Machine Learning

This repository contains the Jupyter Notebook and related resources for the study:

**"Pinpointing Pathogenic Genetic Variants in Early-Onset POAG via Whole Exome Sequencing and Machine Learning Prediction"**

---

## Background
Primary open-angle glaucoma (POAG) is the **second leading cause of irreversible blindness** worldwide.  
Most studies emphasize **late-onset POAG**, while **early-onset POAG (EOG)** shows stronger heritability and higher penetrance.

We developed a **family-based machine learning framework**:
- **Training** on 19 two-generation familial EOG pedigrees
- **Validation** on sporadic early-onset cases
- **Testing** against independent controls and extended datasets

---

## Methodology

### 1. Variant Filtering
- Whole-exome sequencing (WES) from 19 families and sporadic cases  
- Filters: **family frequency >0.2, sporadic >0.2, controls <0.6, CADD >5**  
- Final panel: **3,054 exonic SNPs**

### 2. Dataset Partitioning

| Dataset      | Composition                                                                 | Sample Size (n) |
|--------------|------------------------------------------------------------------------------|-----------------|
| Training     | 46 familial cases (24 FE, 22 FL) + 36 controls (12 family controls, 10 elderly, 14 TWB) | 82 |
| Validation   | 18 sporadic early-onset (SE) + 11 TWB controls (randomly allocated)          | 29 |
| Testing      | Remaining 18 SE + 11 TWB controls (independent of validation)                | 29 |
| Extended     | 6 sporadic late-onset (SL) + 21 TWB late-onset + 10 suspects                 | 37 |

**Random Allocation Principles**
- Familial samples restricted to **Training only** → prevents data leakage via kinship  
- SE and TWB controls randomly assigned to **Validation** or **Testing** in each iteration  
- **Validation** used only for feature ranking & model selection  
- **Testing** used only for final performance evaluation  
- Entire process repeated **500 Monte Carlo iterations** for robustness

### 3. Feature Ranking
- Random Forest classifier applied on **Validation set**  
- Importance measured by **Gini impurity (mean decrease in impurity)**  
- Each iteration: **200 repeats** → averaged for stability  
- Aggregated across **500 iterations** → robust final SNP ranking

### 4. Model Training & Evaluation
- Trained on **Training set**, with feature count chosen via **Validation**  
- Evaluated on **independent Testing set**  
- **Extended dataset** assessed via probability distributions (not included in confusion matrices)  
- Metrics: **Accuracy, Recall, Confusion Matrix, Probability Distributions**

---

## Key Findings
- Testing set performance (500 iterations):  
  - **Accuracy = 0.946 (mean)**  
  - **Recall = 0.912 (mean)**  
  - **83/500 runs achieved 100% accuracy**

- **Predictive Probabilities**  
  - Familial early-onset (FE): ~86%  
  - Familial late-onset (FL): ~86%  
  - Sporadic early-onset (SE): ~62%  
  - Controls: ~25%  
  - Sporadic late-onset (SL): ~35%  
  - Suspects: ~66%

- **Top 200 SNPs** converge on five biological mechanisms:  
  1. Cilia biogenesis  
  2. Mitochondrial dysfunction  
  3. Hedgehog signaling  
  4. Neurotrophic regulation  
  5. Autophagy

---

## Files
- `NC_ML_model.ipynb` – main notebook (preprocessing, feature ranking, model training, evaluation)  
- Input File: 3054SNPs.csv or 3054SNPs.zip

---

## Data Availability
- **Raw WES data not publicly available** (privacy regulations)  
- Processed SNP matrices (**3,054 variants**) available upon reasonable request  

---

## Contact
- **Hao-Chen Tseng** (409030002@mail.ndmctsgh.edu.tw)  
- **Prof. Yu Chuan Huang (NDMC)**
