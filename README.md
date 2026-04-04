# causal-promo-opt
Causal modeling to optimize promotion strategies (discounts, tech support) for revenue growth using Double Machine Learning and Propensity Score Matching.

1. Build DAGs, identifying confounders and treatments.
2. Applied refutation tests to 3 Linear Double-Machine Learning models, to check robustness
of confounder assumptions on the treatments (provide tech support, provide discount, and provide both)
3. Focused on modeling CATE using Causal Forests.  First, assumed range of cost associated
with each application of a discount and tech support. Built Causal Forests on this
adjusted revenue.
4. Determined optimal CATE based on model results.
5. Determined whether to apply recommended intervention by accounting for
policy constraints.  Added the treatment if share in cate / past revenue exceeds
15%.  Removed treatment if cate/past revenue share exceeds 25%.
6. Ran trees on holdout set to estimate the overall lift.
