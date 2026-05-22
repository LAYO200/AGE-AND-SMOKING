# Age and Smoking — A Frequentist and Bayesian Analysis

**Kiana Philpott, Chizurum Ewelike, Oluwatomilayo Faloseyi** · STAT 3910 · University of Prince Edward Island

🔗 [View the full analysis](https://layo200.github.io/AGE-AND-SMOKING/)

---

## Overview

This project investigates the age demographics of smokers in the United Kingdom using both Frequentist and Bayesian statistical methods. The central question is whether the average age of smokers is 60 years old — and if not, how far below that threshold the true mean falls.

Both approaches were applied independently and compared, demonstrating how different statistical frameworks can be used to test the same hypothesis and arrive at consistent conclusions.

---

## Research Question

**Is the average age of smokers 60 years old?**

| Hypothesis | Statement |
|---|---|
| H₀ (Null) | The mean age of smokers is 60 years |
| H₁ (Alternative) | The mean age of smokers is less than 60 years |

---

## Dataset

- **Source**: [Smoking Dataset from UK — Kaggle](https://www.kaggle.com/datasets/utkarshx27/smoking-dataset-from-uk?resource=download)
- **Size**: 1,691 observations · 12 variables
- **Format**: CSV

Variables retained for analysis: age, gender, smoking status (`smoke`), and cigarette type (`type`). Demographic variables (marital status, income, region, etc.) were removed as they were not relevant to the research question.

---

## Methods

### Frequentist Analysis

A one-sample t-test was used to assess whether the mean age of smokers is significantly less than 60. Before proceeding, two key assumptions were checked:

- **Normality** — verified visually via histogram; the distribution is approximately bell-shaped, and the large sample size ensures the Central Limit Theorem applies
- **Outliers** — confirmed absent via boxplot and IQR test

### Bayesian Analysis

A Bayesian one-sample t-test was conducted using the **Jeffreys prior** — a non-informative prior chosen to let the data drive the posterior distribution without imposing strong prior beliefs. The Shapiro-Wilk test revealed minor deviations from normality, but the large sample size justifies proceeding under the CLT. The Bayes Factor was then computed to quantify the strength of evidence against the null hypothesis.

---

## Results

Both approaches led to the same conclusion:

| Method | Key Statistic | Outcome |
|---|---|---|
| Frequentist t-test | t = −22.31, p ≈ 4.00e-97 | Reject H₀ |
| Cohen's d | d = −0.542 | Moderate effect size |
| Bayesian t-test | t = −21.92, credible interval: (−∞, 44.01) | Reject H₀ |
| Bayes Factor | BF ≈ 9.97 × 10⁹² | Overwhelming evidence for H₁ |

The estimated mean age of smokers is approximately **42 years**, well below the hypothesized 60. The 95% credible interval confirms that the true mean age is likely below 44 years.

---

## Key Findings

- The average age of smokers is significantly less than 60 — both methods agree with very high confidence
- Smoking prevalence peaks in the **35–50 age range**, with a gradual decline after age 50
- The Frequentist and Bayesian approaches produced consistent results, reinforcing confidence in the conclusion
- The Jeffreys prior was appropriate here as no strong prior information about smoker age demographics was available

---

## Comparing the Two Approaches

| | Frequentist | Bayesian |
|---|---|---|
| Decision basis | p-value < 0.05 threshold | Bayes Factor & credible interval |
| Uncertainty | Confidence interval | Credible interval |
| Prior beliefs | Not incorporated | Explicitly modelled (Jeffreys) |
| Conclusion | Reject H₀ | Reject H₀ |

Despite their methodological differences, both approaches arrived at the same conclusion — a useful demonstration of statistical robustness.

---

## Repository Structure

```
├── 3910FinalProject.Rmd     # Full R Markdown source (analysis + code)
├── index.html               # Rendered HTML report (live page)
├── README.md
```

---

## Tools

R · ggplot2 · BayesFactor · Bolstad · dplyr · janitor
