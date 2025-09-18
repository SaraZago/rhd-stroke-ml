# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |     MSE |    RMSE |     MAE |
|-------:|-----------:|--------:|--------:|--------:|
|      1 |  -0.483353 | 455.783 | 21.3491 | 19.4829 |
|      2 |  -0.73682  | 201.278 | 14.1873 | 10.7383 |
|      3 | -15.8178   | 368.123 | 19.1865 | 18.075  |
|      4 |  -0.493936 | 264.302 | 16.2574 | 14.37   |
|      5 |  -0.292942 | 392.803 | 19.8193 | 19.035  |

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
- Media R² sui fold: -3.565 (± 6.851).
- Errore medio: RMSE = 18.160, MAE = 16.340 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 6.851).
- Stabilità media delle importanze tra fold: 0.039 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TL (0.156), FL (0.146), PR (0.139).

Miglior fold
- Best fold: 5 con R² = -0.293.
- Nella best fold le feature più importanti sono: FL (0.201), TL (0.124), TR (0.121).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.560 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.202 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
