# Genetic Prediction Model for Early-Onset POAG using Whole-Exome Sequencing and Machine Learning

This repository contains the Jupyter Notebook and related resources for the study:

**"Pinpointing Pathogenic Genetic Variants in Early-Onset POAG via Whole Exome Sequencing and Machine Learning Prediction "**

## 🧬 Background

Primary open-angle glaucoma (POAG) is the second leading cause of irreversible blindness. Most genetic studies have focused on late-onset POAG, but early-onset cases (EOG) show stronger heritability and higher penetrance. To address this gap, we developed a machine learning framework trained on 18 familial EOG pedigrees and tested on 22 sporadic EOG cases.

## 🛠️ Methodology

- **Variant Filtering**: Whole-exome sequencing (WES) data were filtered based on family frequency, control exclusion, and functional annotation (CADD > 5).
- **Feature Ranking**: 3,054 SNPs were prioritized using Random Forest importance scores.
- **Model Building**: Logistic Regression and Random Forest models were trained on familial data and tested on sporadic and population-based controls (TWB).
- **Evaluation**: Accuracy, recall, PCA projection, and predictive probabilities were used to assess model performance.

## 📈 Key Findings

- A 100-SNP panel achieved 100% accuracy and recall in predicting early-onset POAG.
- Predictive probabilities were elevated in FE-, FL-, and SE-POAG subgroups, but significantly lower in late-onset and control groups.


## 📂 Files

- `0516NC_Code.ipynb`: Main notebook containing preprocessing, feature selection, modeling, and visualization.




## 🔒 Data Availability

Due to privacy concerns, raw WES data are not publicly available. Processed variant data may be available upon reasonable request to the corresponding author.

## 📬 Contact

For inquiries, please contact **Hao-Chen Tseng** (409030002@mail.ndmctsgh.edu.tw) or **Yu Chuan Huang** (PI, NDMC).

