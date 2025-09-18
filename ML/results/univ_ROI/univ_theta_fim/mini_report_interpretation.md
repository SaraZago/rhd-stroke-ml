# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |          R2 |     MSE |    RMSE |      MAE |
|-------:|------------:|--------:|--------:|---------:|
|      1 |  -0.752206  | 538.392 | 23.2033 | 19.56    |
|      2 |   0.0740107 | 107.312 | 10.3591 |  7.79667 |
|      3 | -14.761     | 344.991 | 18.5739 | 16.3867  |
|      4 |   0.300719  | 123.714 | 11.1227 | 10.0033  |
|      5 |  -0.0693385 | 324.871 | 18.0242 | 16.015   |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| OR        |         0.14553   |        0.0216313 |
| TL        |         0.144669  |        0.0330713 |
| TR        |         0.106194  |        0.017804  |
| CR        |         0.105932  |        0.0297038 |
| PR        |         0.0982315 |        0.0234475 |
| PL        |         0.0961189 |        0.0422115 |
| CL        |         0.0913789 |        0.0299446 |
| FL        |         0.0757899 |        0.0263554 |
| FR        |         0.0692369 |        0.0257403 |
| OL        |         0.0669184 |        0.0100994 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -3.042 (± 6.563).
- Errore medio: RMSE = 16.257, MAE = 13.952 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 6.563).
- Stabilità media delle importanze tra fold: 0.026 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: OR (0.146), TL (0.145), TR (0.106).

Miglior fold
- Best fold: 4 con R² = 0.301.
- Nella best fold le feature più importanti sono: TL (0.153), PL (0.146), TR (0.125).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.427 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.806 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
