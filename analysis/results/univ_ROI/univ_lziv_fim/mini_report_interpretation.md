# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |     RMSE |     MAE |
|-------:|-----------:|---------:|---------:|--------:|
|      1 |  0.0285598 | 298.49   | 17.2769  | 13.2457 |
|      2 |  0.448081  |  63.9613 |  7.99758 |  6.855  |
|      3 | -7.51056   | 186.287  | 13.6487  | 11.2983 |
|      4 | -0.196405  | 211.664  | 14.5487  | 13.1283 |
|      5 | -0.0809935 | 328.412  | 18.1221  | 17.7367 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| CL        |         0.179499  |       0.0440395  |
| PR        |         0.161591  |       0.0764601  |
| TL        |         0.153691  |       0.0683992  |
| FL        |         0.149251  |       0.052949   |
| OR        |         0.0888531 |       0.0280999  |
| PL        |         0.0650878 |       0.0302021  |
| OL        |         0.0585316 |       0.00859932 |
| CR        |         0.0519733 |       0.0187419  |
| TR        |         0.0479641 |       0.0076071  |
| FR        |         0.0435572 |       0.0112052  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.462 (± 3.390).
- Errore medio: RMSE = 14.319, MAE = 12.453 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 3.390).
- Stabilità media delle importanze tra fold: 0.035 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: CL (0.179), PR (0.162), TL (0.154).

Miglior fold
- Best fold: 2 con R² = 0.448.
- Nella best fold le feature più importanti sono: FL (0.199), CL (0.196), TL (0.179).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.080 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.818 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
