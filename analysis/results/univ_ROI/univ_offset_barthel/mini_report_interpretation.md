# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.650216 | 1254.5   | 35.4189 | 28.2214 |
|      2 | -1.81897  |  602.945 | 24.5549 | 17.725  |
|      3 | -3.40823  |  428.578 | 20.7021 | 16.8083 |
|      4 | -5.15474  |  615.474 | 24.8087 | 22.0583 |
|      5 | -0.55023  | 1253.1   | 35.3992 | 32.7833 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PL        |         0.156439  |        0.0400834 |
| CR        |         0.145127  |        0.0416128 |
| OL        |         0.128082  |        0.121669  |
| TL        |         0.120132  |        0.0484459 |
| OR        |         0.0978676 |        0.0139476 |
| FL        |         0.0930031 |        0.033756  |
| TR        |         0.0705905 |        0.0091971 |
| PR        |         0.0638719 |        0.0266527 |
| CL        |         0.0624659 |        0.0123779 |
| FR        |         0.0624209 |        0.0235215 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -2.316 (± 1.962).
- Errore medio: RMSE = 28.177, MAE = 23.519 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.962).
- Stabilità media delle importanze tra fold: 0.037 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PL (0.156), CR (0.145), OL (0.128).

Miglior fold
- Best fold: 5 con R² = -0.550.
- Nella best fold le feature più importanti sono: OL (0.341), PL (0.096), TR (0.086).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.675 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.267 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
