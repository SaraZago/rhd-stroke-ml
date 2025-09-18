# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.554468 | 1181.71  | 34.3761 | 29.8    |
|      2 | -1.2939   |  490.64  | 22.1504 | 20.1    |
|      3 | -7.84502  |  859.933 | 29.3246 | 27.0083 |
|      4 | -2.98355  |  398.355 | 19.9588 | 16.175  |
|      5 | -0.306958 | 1056.46  | 32.5032 | 29.5167 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| CL        |         0.154855  |        0.0338028 |
| FR        |         0.11562   |        0.0460467 |
| TR        |         0.114554  |        0.0621084 |
| FL        |         0.113444  |        0.0449148 |
| CR        |         0.110412  |        0.0362547 |
| PR        |         0.0973903 |        0.0210098 |
| PL        |         0.0787683 |        0.0459042 |
| TL        |         0.0754531 |        0.0267661 |
| OL        |         0.0733783 |        0.0462598 |
| OR        |         0.0661241 |        0.0143104 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -2.597 (± 3.115).
- Errore medio: RMSE = 27.663, MAE = 24.520 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 3.115).
- Stabilità media delle importanze tra fold: 0.038 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: CL (0.155), FR (0.116), TR (0.115).

Miglior fold
- Best fold: 5 con R² = -0.307.
- Nella best fold le feature più importanti sono: CR (0.170), FL (0.149), FR (0.146).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.521 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.741 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
