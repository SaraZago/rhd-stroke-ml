# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |     RMSE |      MAE |
|-------:|-----------:|---------:|---------:|---------:|
|      1 | -0.577577  | 484.735  | 22.0167  | 18.1114  |
|      2 |  0.501806  |  57.7351 |  7.59836 |  6.56333 |
|      3 | -9.25065   | 224.375  | 14.9792  | 13.76    |
|      4 | -0.534216  | 271.428  | 16.4751  | 13.9767  |
|      5 |  0.0823174 | 278.797  | 16.6972  | 15.495   |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| TL        |         0.156413  |        0.0624985 |
| FL        |         0.145636  |        0.0614991 |
| PR        |         0.138893  |        0.0649213 |
| TR        |         0.122589  |        0.0114282 |
| OL        |         0.0996879 |        0.0471293 |
| OR        |         0.0835674 |        0.025648  |
| CL        |         0.0797622 |        0.0310305 |
| PL        |         0.0616063 |        0.0307368 |
| FR        |         0.0560864 |        0.0279037 |
| CR        |         0.0557578 |        0.0306285 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.956 (± 4.103).
- Errore medio: RMSE = 15.553, MAE = 13.581 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 4.103).
- Stabilità media delle importanze tra fold: 0.039 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TL (0.156), FL (0.146), PR (0.139).

Miglior fold
- Best fold: 2 con R² = 0.502.
- Nella best fold le feature più importanti sono: TL (0.184), FL (0.132), OL (0.124).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.056 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.493 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
