---
## Quickstart


# Clone the repository
git clone https://github.com/sboakye-yiadom/e-lightgbm-mobile-money-fraud-ghana.git
cd e-lightgbm-mobile-money-fraud-ghana

# Install dependencies
pip install -r requirements.txt

# Run baseline first (Phase 1 — lock before touching Phase 2)
jupyter notebook notebooks/01_baseline_lightgbm.ipynb

# Run engineered model (Phase 2 — separate notebook, same seed)
jupyter notebook notebooks/02_e_lightgbm_focal_loss.ipynb
```

---

## Reproducibility

| Item | Value |
|---|---|
| Python version | 3.10 |
| Random seed | 42 (fixed across all runs — never change) |
| Data split | 70 / 15 / 15 stratified by fraud label |
| Cross-validation | 5-fold stratified CV |
| Computing environment | Google Colab Pro (NVIDIA A100 / T4, 25 GB RAM) |
| Checkpointing | Every 50 boosting rounds, saved to Google Drive |

**Library versions (pinned):**
lightgbm==4.3.0

xgboost==2.0.3

scikit-learn==1.4.0

shap==0.44.0

pandas==2.1.4

numpy==1.26.3

matplotlib==3.8.2

---

## Dataset

The primary dataset consists of provider-verified Ghanaian mobile money transaction
logs (target: 35,000 records; minimum: 25,000; stretch: 50,000), collected under a
data-sharing agreement with a Ghanaian mobile money operator. Data is pre-anonymised
at source before transfer to the research team.

**Raw data is not included in this repository** in accordance with the data-sharing
agreement and KNUST data protection policy. The `data/README_data.md` file documents
the anonymised field schema for reproducibility purposes.

The PaySim public dataset is used for baseline hyperparameter tuning only and is not
the primary evaluation source.

---

## Results (Planned — to be updated post-experiment)

| Metric | Baseline LightGBM | E-LightGBM | Δ Change | p-value |
|---|---|---|---|---|
| AUC-PR | — | — | — | — |
| AUC-ROC | — | — | — | — |
| Macro F1 | — | — | — | — |
| Fraud Recall | — | — | — | — |
| Training Time (s) | — | — | — | — |

*Results will be populated upon experiment completion. Pre-registered hypothesis: ΔAUC-PR = +0.03 to +0.05 over the log-loss baseline.*

---

## Ethics

This study was approved by the Kwame Nkrumah University of Science and Technology
Committee on Human Research, Publications and Ethics (CHRPE),
approval number **[to be inserted upon approval]**.

No individually identifiable end-user data was collected or accessed by the research
team. All transaction records were pre-anonymised by the provider prior to transfer.
Data is stored on encrypted storage accessible only to the research team and will be
retained in the KNUST Department of Computer Science repository for five years
post-publication, consistent with Section 19 of the KNUST Policy on Publication.

---

## Target Journals

| Priority | Journal | Indexing |
|---|---|---|
| Primary | Expert Systems with Applications (Elsevier) | Scopus / WoS Q1, IF ~8.5–10.5 |
| Secondary | Decision Support Systems (Elsevier) | Scopus / WoS Q1 |
| Tertiary | Engineering Applications of Artificial Intelligence (Elsevier) | Scopus / WoS Q1 |

---

## Citation

If you reference this work, please cite:

> Boakye-Yiadom, S. (2026). *An engineered LightGBM-SHAP model for mobile money
> fraud detection in Ghana: A focal-loss approach* [Research proposal].
> Department of Computer Science, Kwame Nkrumah University of Science and Technology.

Zenodo DOI: *[to be registered upon first code release]*

---

## License

**Code:** MIT License — see `LICENSE` file.  
**Data:** Not included in this repository — see Dataset section above.
