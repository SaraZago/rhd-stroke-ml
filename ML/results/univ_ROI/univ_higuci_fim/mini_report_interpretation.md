# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |     MSE |    RMSE |      MAE |
|-------:|-----------:|--------:|--------:|---------:|
|      1 |  -0.251405 | 384.513 | 19.609  | 16.7143  |
|      2 |   0.250886 |  86.814 |  9.3174 |  8.01833 |
|      3 | -17.803    | 411.577 | 20.2874 | 17.64    |
|      4 |   0.197419 | 141.99  | 11.916  | 10.0667  |
|      5 |  -0.224169 | 371.909 | 19.285  | 16.975   |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PR        |         0.141738  |       0.0504249  |
| CL        |         0.121359  |       0.0305357  |
| OR        |         0.111642  |       0.0475928  |
| OL        |         0.106795  |       0.0615798  |
| FL        |         0.101293  |       0.0565145  |
| TR        |         0.0992799 |       0.00873218 |
| TL        |         0.0975762 |       0.0298988  |
| FR        |         0.088603  |       0.0454267  |
| CR        |         0.0660223 |       0.00878263 |
| PL        |         0.0656928 |       0.0407685  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -3.566 (± 7.962).
- Errore medio: RMSE = 16.083, MAE = 13.883 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 7.962).
- Stabilità media delle importanze tra fold: 0.038 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PR (0.142), CL (0.121), OR (0.112).

Miglior fold
- Best fold: 2 con R² = 0.251.
- Nella best fold le feature più importanti sono: PR (0.175), CL (0.118), TL (0.116).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.013 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.551 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
