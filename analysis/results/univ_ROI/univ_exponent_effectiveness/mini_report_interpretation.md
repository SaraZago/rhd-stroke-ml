# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.645874 | 1446.3   | 38.0303 | 32.8008 |
|      2 |  0.254583 |  368.367 | 19.1929 | 15.7706 |
|      3 | -1.94456  |  714.013 | 26.721  | 22.199  |
|      4 | -1.16975  |  496.497 | 22.2822 | 19.3661 |
|      5 | -0.217126 | 1040.94  | 32.2636 | 27.2838 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PR        |         0.149883  |        0.0500545 |
| TL        |         0.127779  |        0.0458939 |
| OL        |         0.118215  |        0.0440769 |
| TR        |         0.106647  |        0.0215025 |
| FR        |         0.0969711 |        0.0324463 |
| FL        |         0.0897373 |        0.0266781 |
| CR        |         0.0869818 |        0.0224389 |
| PL        |         0.0858026 |        0.0373285 |
| CL        |         0.0746065 |        0.0202857 |
| OR        |         0.0633771 |        0.010894  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.745 (± 0.852).
- Errore medio: RMSE = 27.698, MAE = 23.484 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 0.852).
- Stabilità media delle importanze tra fold: 0.031 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PR (0.150), TL (0.128), OL (0.118).

Miglior fold
- Best fold: 2 con R² = 0.255.
- Nella best fold le feature più importanti sono: TL (0.183), PR (0.163), CR (0.118).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.019 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.676 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
