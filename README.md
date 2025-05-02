# Order Flow Imbalance (OFI) Feature Construction

This repository contains code and analysis for constructing and evaluating Order Flow Imbalance (OFI) features, based on the research paper:

> *Cross-Impact of Order Flow Imbalance in Equity Markets*  
> by Rama Cont, Mihai Cucuringu, and Chao Zhang

## 📌 Project Objectives

The primary goal is to compute the following OFI features from limit order book (LOB) data, with one value per second:

- **Best-Level OFI**: Imbalance at the top of the book (level 0)
- **Multi-Level OFI**: Raw OFI vectors from LOB levels 1 to 10
- **Integrated OFI**: A PCA-compressed representation of multi-level OFI
- **Cross-Asset OFI**: Simulated using a noise-correlated proxy due to single-asset data constraints

Each feature is aligned with the paper's definitions and aggregated at the 1-second interval level.

---

## 📂 Repository Contents

| File | Description |
|------|-------------|
| `OFI_Feature_Engineering_Task.ipynb` | Clean, modular script to compute all OFI features |
| `ofi_conceptual_answers.pdf` | Written answers to conceptual questions |
| `first_25000_rows.csv` | Sample LOB data used for feature construction |

---

## 🧠 Conceptual Highlights

- **Multi-Level OFI** captures latent liquidity and improves explanatory power for price impact.
- **Lasso regression** is preferred for estimating cross-impact due to its sparsity-inducing behavior in high-dimensional settings.
- **OFI outperforms trade volume** for predicting short-term returns due to its directional sensitivity.

See [`ofi_conceptual_answers.pdf`](ofi_conceptual_answers.pdf) for full explanations.

---

## 📊 Insights & Analysis

In addition to feature construction, exploratory insights were generated:

- Best-Level OFI shows directional alignment with forward returns.
- Integrated OFI demonstrates strong predictive patterns around mid-price movement.
- Normalized OFI smooths volatility while retaining directional signals.

Plots and interpretations are available in the notebook.

---

## 🛠 How to Run

Clone the repo and run the OFI_Feature_Engineering_Task:

```bash
python OFI_Feature_Engineering_Task.ipynb
