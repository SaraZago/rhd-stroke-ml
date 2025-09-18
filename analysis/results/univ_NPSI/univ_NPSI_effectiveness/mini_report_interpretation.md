# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |     MAE |
|-------:|-----------:|---------:|--------:|--------:|
|      1 | -0.0982094 |  965.046 | 31.0652 | 27.5272 |
|      2 | -0.136526  |  561.643 | 23.699  | 19.6998 |
|      3 | -2.9891    |  967.299 | 31.1014 | 28.1444 |
|      4 | -1.49474   |  570.864 | 23.8928 | 17.6483 |
|      5 | -0.196133  | 1022.98  | 31.9841 | 26.3375 |

## Importanze (media ± std)

| feature    |   mean_importance |   std_importance |
|:-----------|------------------:|-----------------:|
| semantic   |         0.207086  |        0.0940351 |
| reyword    |         0.162679  |        0.101882  |
| criq       |         0.151815  |        0.0663276 |
| reyfig     |         0.112402  |        0.0337135 |
| denomdescr |         0.0995838 |        0.0448399 |
| phonemic   |         0.0675603 |        0.0146704 |
| span_for   |         0.0625547 |        0.017379  |
| trog       |         0.0577145 |        0.0231708 |
| mmse       |         0.0409713 |        0.0067464 |
| span_back  |         0.0376343 |        0.0142123 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.983 (± 1.265).
- Errore medio: RMSE = 28.349, MAE = 23.871 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.265).
- Stabilità media delle importanze tra fold: 0.042 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: semantic (0.207), reyword (0.163), criq (0.152).

Miglior fold
- Best fold: 1 con R² = -0.098.
- Nella best fold le feature più importanti sono: criq (0.176), denomdescr (0.174), reyword (0.131).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.554 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.438 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
