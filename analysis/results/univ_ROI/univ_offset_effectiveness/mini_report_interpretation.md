# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.601681 | 1407.47  | 37.5162 | 34.3046 |
|      2 | -0.371364 |  677.694 | 26.0326 | 20.8062 |
|      3 | -2.96768  |  962.105 | 31.0178 | 27.0489 |
|      4 | -2.18462  |  728.728 | 26.995  | 24.8446 |
|      5 | -0.426337 | 1219.86  | 34.9266 | 34.0632 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| CR        |         0.131621  |        0.0364952 |
| PL        |         0.12412   |        0.0467303 |
| OL        |         0.117069  |        0.102127  |
| OR        |         0.115313  |        0.047961  |
| PR        |         0.110081  |        0.0462538 |
| TL        |         0.101262  |        0.0403873 |
| FR        |         0.0853648 |        0.0353232 |
| FL        |         0.0759325 |        0.0187455 |
| CL        |         0.0750756 |        0.0166677 |
| TR        |         0.0641604 |        0.0163461 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.310 (± 1.191).
- Errore medio: RMSE = 31.298, MAE = 28.213 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.191).
- Stabilità media delle importanze tra fold: 0.041 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: CR (0.132), PL (0.124), OL (0.117).

Miglior fold
- Best fold: 2 con R² = -0.371.
- Nella best fold le feature più importanti sono: CR (0.172), OR (0.144), PL (0.141).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.771 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.185 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
