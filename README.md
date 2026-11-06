# Transcriptomic Expression, Survival Outcome, and Genomic Alteration Analysis of TP53 in Breast Invasive Carcinoma (TCGA-BRCA)

## 📌 Project Overview
This project presents an integrated bioinformatics analysis of the ***TP53*** tumor suppressor gene (encoding Tumor Protein p53, the "Guardian of the Genome") in **Breast Invasive Carcinoma (BRCA)**. Utilizing transcriptomic and clinical outcome data from **The Cancer Genome Atlas (TCGA)** and control samples from **GTEx**, this study evaluates differential gene expression, Kaplan-Meier overall survival prognostics, and somatic mutation frequencies.

---

## 🎯 Research Objectives & Hypotheses
* **Expression Profiling:** Compare *TP53* mRNA expression levels between primary breast adenocarcinoma tissue and non-cancerous solid normal control tissue.
* **Prognostic Impact:** Assess whether *TP53* transcript expression levels correlate with overall patient survival outcomes.
* **Genomic Verification:** Identify the frequency and specific types of driver mutations occurring across the *TP53* gene sequence in breast cancer cohorts.
* **Hypothesis:** *TP53* gene expression is significantly altered in tumor tissue relative to normal breast tissue, and elevated *TP53* expression correlates with poorer overall patient survival due to the accumulation of non-functional mutant protein variants.

---

## 🛠️ Data Sources & Web-Based Bioinformatics Tools
* **Primary Cohorts:** TCGA-BRCA ($n = 1,085$ primary tumors) matched with TCGA normal ($n = 112$) and GTEx healthy breast tissue controls ($n = 179$) ($n_{\text{total control}} = 291$).
* **GEPIA2 (Gene Expression Profiling Interactive Analysis):** Utilized for RNA-seq log scale normalization ($\log_2(\text{TPM} + 1)$), differential expression box plots, and Kaplan-Meier overall survival curves with log-rank testing.
* **cBioPortal for Cancer Genomics:** Utilized for OncoPrint alteration frequency profiling and lollipop structural mutation mapping across the *TP53* domain structure.

---

## 📊 Key Results & Quantitative Calculations

### 1. Differential Transcriptomic Expression (Tumor vs. Normal)
* **Tumor Cohort Median Expression ($n = 1,085$):** $\approx 5.40 \text{ Log}_2(\text{TPM} + 1)$
* **Normal Cohort Median Expression ($n = 291$):** $\approx 4.70 \text{ Log}_2(\text{TPM} + 1)$
* **Log₂ Fold Change ($\Delta\text{Median}$):** $5.40 - 4.70 = \mathbf{0.70}$
* **Relative Fold Increase:** $2^{0.70} \approx \mathbf{1.62\times}$
* **Finding:** *TP53* mRNA transcript expression is **1.62-fold higher** in breast carcinoma tissue compared to healthy controls ($|\text{Log}_2\text{FC}| \ge 1.0, p < 0.01$).

### 2. Kaplan-Meier Overall Survival (OS) Analysis
* **Cohort Stratification:** High *TP53* expression ($n = 535$) vs. Low *TP53* expression ($n = 535$).
* **Hazard Ratio ($\text{HR}$):** $\text{HR}(\text{high}) = 1.40 \quad (\text{Log-rank } p = 0.038)$
* **Mortality Risk Increase:** $(1.40 - 1.0) \times 100\% = \mathbf{40\%}$
* **Median Survival Milestones:** High expression group drops to $50\%$ survival at **$\approx 120$ months (~10.0 years)**, whereas the low expression group maintains $> 50\%$ survival past **$> 220$ months (>18.3 years)** ($\Delta = \text{100 months / ~8.3 years}$).
* **Finding:** Elevated *TP53* expression is a statistically significant poor prognostic factor, conferring a **40% higher hazard of mortality** at any given point in time.

### 3. Somatic Mutation Profiling via cBioPortal
* **Alteration Frequency:** *TP53* is altered in **35%** ($351 / 996$ samples) of TCGA-BRCA patients.
* **Mutation Types:** Predominantly missense mutations ($213$ samples) and truncating driver mutations ($105$ samples), concentrated around the p53 DNA-binding domain (e.g., hotspot residue R273H/C/L).

---

## 💡 Biological Insights
Contrary to the intuitive model that tumor suppressor genes are completely silenced in cancer, *TP53* mRNA transcript levels are significantly upregulated in primary breast tumors. This paradox is explained by missense mutations in the DNA-binding domain: mutant p53 proteins lose their standard MDM2-mediated negative feedback degradation, stabilizing inside the cell. The tumor cell transcriptionally compensates by over-producing *TP53* mRNA, ultimately driving aggressive tumor phenotypes, chemoresistance, and reduced overall patient survival.

---

## 📈 Quantitative Summary Table

| Metric | High Expression / Tumor | Low Expression / Normal | Statistical Significance |
|---|---|---|---|
| **Median Expression** | $5.40 \text{ Log}_2\text{TPM}$ | $4.70 \text{ Log}_2\text{TPM}$ | $p < 0.01 \quad (\text{FC} = 1.62\times)$ |
| **Cohort Sample Size ($n$)** | $535 \text{ patients}$ | $535 \text{ patients}$ | $N = 1,070 \text{ total cohort}$ |
| **Hazard Ratio (HR)** | $1.40$ | $1.00 \text{ (Baseline)}$ | Log-rank $p = 0.038$ |
| **Median Survival** | $\approx 120 \text{ months}$ | $> 220 \text{ months}$ | Log-rank $p = 0.038$ |
| **Mutation Rate** | $35\% \text{ alteration frequency}$ | — | Driver mutations (Missense/Truncating) |

---

## 📂 Repository Contents
- `PROJECT_file.docx` — Complete written research report draft[cite: 4].
- `TP53_boxplot_FH1Je.pdf` — High-resolution GEPIA2 gene expression box plot output[cite: 2].
- `TP53_survival_2ohDv.pdf` — GEPIA2 Kaplan-Meier overall survival plot[cite: 3].
- `cBioPortal_OncoPrint.png` — Alteration frequency OncoPrint visualization[cite: 4].
- `cBioPortal_Mutations.png` — Lollipop mutation domain map for *TP53*[cite: 4].

---

## 🧠 Personal Learning Outcomes
1. **Multi-Omics Data Integration:** Mastered accessing, processing, and harmonizing transcriptomic RNA-seq data, patient survival curves, and genomic mutation maps using web-based tools (GEPIA2, cBioPortal, TCGA).
2. **Biostatistical Proficiency:** Gained practical experience deriving Log₂ Fold Change ratios, calculating hazard ratios from clinical cohorts, interpreting $p$-values, and estimating median survival milestones.
3. **Genomic Literacy:** Learned to connect raw molecular data to clinical outcomes, understanding how mutant p53 accumulation drives poor cancer prognosis.
