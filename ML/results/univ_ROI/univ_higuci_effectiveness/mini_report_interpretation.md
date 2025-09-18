# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |     MAE |
|-------:|-----------:|---------:|--------:|--------:|
|      1 | -0.654812  | 1454.16  | 38.1334 | 36.0534 |
|      2 | -0.606199  |  793.744 | 28.1735 | 25.9318 |
|      3 | -4.15681   | 1250.45  | 35.3617 | 31.4358 |
|      4 | -1.24527   |  513.779 | 22.6667 | 17.0207 |
|      5 | -0.0620905 |  908.345 | 30.1388 | 25.9049 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| FL        |         0.142685  |       0.0884998  |
| CL        |         0.135084  |       0.0268847  |
| TR        |         0.117087  |       0.0229085  |
| PR        |         0.101152  |       0.0324403  |
| PL        |         0.099758  |       0.0461449  |
| OL        |         0.0879932 |       0.0426013  |
| TL        |         0.0827688 |       0.0177915  |
| FR        |         0.0805024 |       0.0322064  |
| OR        |         0.0771445 |       0.00982298 |
| CR        |         0.0758251 |       0.0141104  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.345 (± 1.627).
- Errore medio: RMSE = 30.895, MAE = 27.269 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.627).
- Stabilità media delle importanze tra fold: 0.033 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: FL (0.143), CL (0.135), TR (0.117).

Miglior fold
- Best fold: 5 con R² = -0.062.
- Nella best fold le feature più importanti sono: PL (0.166), FL (0.126), TR (0.112).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.238 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.027 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
