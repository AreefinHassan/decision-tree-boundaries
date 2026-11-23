# Decision Tree Boundaries

A visual analysis of decision boundaries for two decision trees classifying
two-dimensional data into Class A and Class B, and an accuracy comparison
between them.

## The two trees

**Tree (a) — a single split on x**

- Split: `x < 0.5` → Class B; otherwise Class A.
- The decision boundary is a single vertical line at `x = 0.5`. The feature
  `y` plays no role in this tree.

**Tree (b) — splits on x, then on y**

- First split: `x < 0.5`. Inside that branch, a second split: `y < 0.5`.
- The boundary is a vertical dashed line at `x = 0.5` plus a horizontal
  dashed line at `y = 0.5` that applies only where `x < 0.5`.
- Regions:
  - `x ≥ 0.5` → Class A
  - `x < 0.5` and `y ≥ 0.5` → Class B
  - `x < 0.5` and `y < 0.5` → Class A

## Accuracy comparison

Neither tree as drawn classifies the data correctly:

- Tree (a) misclassifies every data point, because it relies on a single
  boundary on `x` alone.
- Tree (b) adds complexity by considering both `x` and `y`, yet still
  misclassifies every point except `(0, 0)`.

Both trees therefore perform equally in accuracy, so the simpler model wins:
Tree (a) is preferred on grounds of simplicity.

## Fixing the labels

Swapping the class labels — assigning Class A where `x < 0.5` and Class B
where `x ≥ 0.5` — makes the single-split tree classify all data points
correctly. The report includes a diagram of the corrected boundary.

## Files

```
├── README.md
└── report/
    ├── Decision_Tree_Boundaries.docx   # Full write-up with boundary plots
    └── Decision_Tree_Boundaries.pdf    # PDF version of the same write-up
```
