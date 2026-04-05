# Causal Promotion Optimization

Causal modeling framework to optimize customer promotion strategies (discounts and tech support) for revenue growth using Double Machine Learning (DML) and Causal Forests.

**Projected 8–10% revenue uplift via cost-aware causal policy optimization**

---

## Objective

Identify the optimal promotion strategy for each customer by estimating heterogeneous treatment effects and applying cost-aware decision rules under realistic business constraints.

---

## Methodology

### 1. Causal Graph & Identification
- Constructed Directed Acyclic Graphs (DAGs) to define relationships between treatments, outcomes, and confounders
- Identified valid backdoor adjustment sets for causal estimation

### 2. Treatment Effect Validation
- Applied Double Machine Learning (DML) to estimate treatment effects for:
  - Discount
  - Tech support
  - Combined treatment
- Conducted refutation tests to validate robustness of causal assumptions

### 3. Heterogeneous Treatment Effects (CATE)
- Trained separate Causal Forest models for each treatment
- Estimated individual-level Conditional Average Treatment Effects (CATE)
- Adjusted revenue to reflect **net impact**, incorporating assumed cost ranges for:
  - Discounts
  - Tech support

### 4. Policy Optimization
- For each customer, selected the treatment with the highest projected uplift (CATE)
- Compared recommended vs. observed treatment and applied decision rules:

  **Add treatment if:**
  CATE / Current Revenue ≥ 15%

  **Remove treatment if:**
  CATE / Current Revenue ≥ 25%


- These thresholds reflect asymmetric business constraints (higher bar for removing benefits)

### 5. Out-of-Sample Evaluation
- Applied the optimized policy to a holdout dataset
- Estimated overall projected revenue uplift under different cost scenarios

---

## Key Techniques

- Double Machine Learning (DML)
- Causal Forests (CATE estimation)
- DAG-based causal identification
- Refutation testing (robustness checks)
- Counterfactual policy simulation

---

## Results

- Projected **~8–10% revenue uplift** under optimized targeting strategy
- Demonstrated strong heterogeneity in treatment effects across customers
- Showed that cost-aware targeting significantly improves decision efficiency

---

## Notes

- Cost assumptions for discounts and tech support were modeled as ranges due to lack of observed cost data
- Results are sensitive to these assumptions and should be interpreted accordingly