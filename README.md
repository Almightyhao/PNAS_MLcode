📘 Genetic Prediction Model for Early-Onset POAG using Whole-Exome Sequencing and Machine Learning

This repository contains the Jupyter Notebook and related resources for the study:

"Pinpointing Pathogenic Genetic Variants in Early-Onset POAG via Whole Exome Sequencing and Machine Learning Prediction"

🧬 Background

Primary open-angle glaucoma (POAG) is the second leading cause of irreversible blindness worldwide.
While most genetic studies emphasize late-onset POAG, early-onset POAG (EOG) demonstrates stronger heritability and higher penetrance.

To address this gap, we developed a family-based machine learning framework, trained on 19 two-generation familial EOG pedigrees, validated on sporadic early-onset cases, and tested against independent controls and external datasets.

🛠️ Methodology

Variant Filtering

Whole-exome sequencing (WES) data from 19 EOG families and sporadic cases.

Filters applied: familial frequency >0.2, sporadic frequency >0.2, control frequency <0.6, CADD >5.

Result: 3,054 prioritized exonic SNPs.

Data Partitioning

Training Set (n=82): 46 familial cases (24 FE, 22 FL) + 36 controls (unaffected relatives, elderly, TWB).

Validation Set (n=29): 18 sporadic EOG (SE) cases + 11 TWB controls.

Testing Set (n=29): independent 18 SE cases + 11 TWB controls.

Extended Dataset (n=37): 6 sporadic late-onset (SL), 21 TWB late-onset, and 10 suspect individuals (for probability only).

Feature Ranking

Random Forest classifiers were trained on the validation set.

Feature importance calculated using mean decrease in impurity (Gini importance).

Each iteration: 200 repeated rankings → averaged for stability.

Repeated across 500 Monte Carlo iterations to obtain robust SNP rankings.

Model Training and Evaluation

Top 10–200 ranked SNPs were incrementally tested.

Best-performing feature count selected on validation.

Final model trained on training set, evaluated on testing set, and assessed on extended dataset (probability only).

Metrics: Accuracy, Recall, Confusion Matrix, Predictive Probability distributions.

📈 Key Findings

The validation-ranked SNP panel yielded stable high performance:

Mean Accuracy = 0.946, Recall = 0.912 across 500 test iterations.

83/500 runs achieved 100% accuracy.

Predictive Probabilities:

FE & FL cases: ~86%

SE cases: ~62%

Controls: ~25%

SL cases: ~35% (heterogeneous)

Suspects: ~66% (elevated risk despite being clinically unconfirmed)

Pathway Enrichment: Top-ranked SNPs converged on 5 biological mechanisms:

Cilia biogenesis

Mitochondrial dysfunction

Hedgehog signaling

Neurotrophic regulation

Autophagy

📂 Files

0826_Code.ipynb – Main notebook for preprocessing, feature ranking, model training, and evaluation.

Supplementary plots and outputs (accuracy, recall curves, PCA, violin plots, SNP heatmaps).

🔒 Data Availability

Due to privacy regulations, raw WES data are not publicly available.
Processed variant matrices (3,054 SNPs) may be shared upon reasonable request to the corresponding author.

📬 Contact

For inquiries, please contact:

Hao-Chen Tseng (409030002@mail.ndmctsgh.edu.tw
)

Prof. Yu Chuan Huang (PI, NDMC)
