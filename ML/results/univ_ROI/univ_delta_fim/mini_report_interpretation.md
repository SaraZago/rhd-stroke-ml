# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |     RMSE |     MAE |
|-------:|----------:|---------:|---------:|--------:|
|      1 | -0.337934 | 411.101  | 20.2756  | 16.8971 |
|      2 |  0.173811 |  95.7461 |  9.78499 |  8.125  |
|      3 | -9.92734  | 239.187  | 15.4657  | 13.5083 |
|      4 | -0.352548 | 239.288  | 15.4689  | 12.2    |
|      5 | -0.219257 | 370.417  | 19.2462  | 18.0433 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| TL        |         0.262098  |        0.0263312 |
| OR        |         0.142937  |        0.0600291 |
| TR        |         0.101463  |        0.0333909 |
| PR        |         0.101388  |        0.029776  |
| PL        |         0.0807536 |        0.0276478 |
| FL        |         0.0764427 |        0.0120319 |
| FR        |         0.0653119 |        0.0179702 |
| OL        |         0.0589945 |        0.0258346 |
| CL        |         0.0560468 |        0.0147074 |
| CR        |         0.0545639 |        0.0160517 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -2.133 (± 4.363).
- Errore medio: RMSE = 16.048, MAE = 13.755 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 4.363).
- Stabilità media delle importanze tra fold: 0.026 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TL (0.262), OR (0.143), TR (0.101).

Miglior fold
- Best fold: 2 con R² = 0.174.
- Nella best fold le feature più importanti sono: TL (0.223), OR (0.213), PR (0.106).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.044 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.150 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
