# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.408458 | 1070.72  | 32.7218 | 24.75   |
|      2 |  0.177829 |  175.853 | 13.261  | 11.1    |
|      3 | -1.49898  |  242.956 | 15.5871 | 11.9083 |
|      4 | -2.63467  |  363.467 | 19.0648 | 14.675  |
|      5 | -0.188336 |  960.572 | 30.9931 | 28.3833 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PR        |         0.250119  |        0.0818153 |
| OL        |         0.110421  |        0.0786157 |
| TL        |         0.109558  |        0.043513  |
| FL        |         0.0952725 |        0.0337949 |
| CL        |         0.0850432 |        0.0361771 |
| PL        |         0.0780905 |        0.020555  |
| TR        |         0.075344  |        0.0231955 |
| FR        |         0.074865  |        0.0482992 |
| CR        |         0.065831  |        0.0300595 |
| OR        |         0.0554564 |        0.0205528 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.911 (± 1.149).
- Errore medio: RMSE = 22.326, MAE = 18.163 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.149).
- Stabilità media delle importanze tra fold: 0.042 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PR (0.250), OL (0.110), TL (0.110).

Miglior fold
- Best fold: 2 con R² = 0.178.
- Nella best fold le feature più importanti sono: PR (0.285), TL (0.162), FL (0.102).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.320 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.022 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
