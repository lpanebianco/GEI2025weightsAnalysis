# Gender Equality Index 2025 - Weight Optimization

The Gender Equality Index (GEI) is a composite indicator to measure the progress of gender equality in the EU, developed by the European Institute for Gender Equality (EIGE). It gives more visibility to areas that need improvement and ultimately supports policy makers to design more effective gender equality measures.

Since its first definition in 2013, the GEI is the result of a geometric mean of six indicators, each of them associated to a different domain: Work, Money, Knowledge, Time, Power, and Health. For the 2025 version, domain weights were obtained through an online survey conducted in the last quarter of 2024, which gathered responses from 125 EIGE stakeholders. Weights were derived using the Analytic Hierarchy Process (AHP), a structured method based on expert judgement. In the 2025 GEI Report, such weights are not published in full precision, but only in a rounded format with 2 decimal places. 

In this notebook, a computational approach to reverse-engineering the Gender Equality Index 2025 domain weights through exhaustive combinatorial analysis. The notebook systematically explores all possible 5-row combinations from the dataset, solves constrained logarithmic linear systems, and identifies optimal high-precision weights (15 decimal places) that best reconstruct the published index values.

## Features

- Exhaustive combinatorial search across all possible data point combinations
- High-precision weight computation (15 decimal places)
- Multiple distance metrics (Euclidean, MAE, MSE, RMSE)
- Robust numerical methods using least-squares optimization

## Requirements
```bash
pip install numpy pandas openpyxl
```

## Methodology

The Gender Equality Index is modeled as a weighted geometric mean:
```
Index = (Work^w₁) × (Money^w₂) × (Knowledge^w₃) × (Time^w₄) × (Power^w₅) × (Health^w₆)
```

where weights sum to 1. The notebook:

1. **Samples** all possible 5-row combinations from the published values of the countries' GEI indicator 
2. **Solves** log-transformed linear systems with sum-to-one constraint
3. **Evaluates** solutions by comparing reconstructed vs. published index values

## Results

The notebook outputs:
- Optimal weight distribution for each dimension
- Row-by-row comparison of predicted vs. actual index values
- Statistical error analysis

## Applications

- Understanding dimensional contributions to gender equality metrics
- Validating official report methodologies
- Exploring alternative weighting schemes
- Supporting policy analysis and research

## License

Apache-2.0 license 

## Citation

If you use this work, please cite the Gender Equality Index 2025 Report and this repository.
