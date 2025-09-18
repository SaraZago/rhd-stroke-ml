# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.881359 | 1653.23  | 40.66   | 33.7084 |
|      2 |  0.459662 |  267.022 | 16.3408 | 13.448  |
|      3 | -3.15846  | 1008.37  | 31.7548 | 28.0788 |
|      4 | -0.681048 |  384.67  | 19.613  | 16.9781 |
|      5 | -0.193499 | 1020.73  | 31.9489 | 28.5407 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| TR        |         0.160274  |       0.0480666  |
| OR        |         0.141693  |       0.0268901  |
| TL        |         0.132531  |       0.0446441  |
| FL        |         0.108413  |       0.0344943  |
| PR        |         0.105855  |       0.0618518  |
| CR        |         0.0898376 |       0.0430448  |
| CL        |         0.0782381 |       0.00887232 |
| PL        |         0.0754161 |       0.0214317  |
| OL        |         0.0710279 |       0.0283834  |
| FR        |         0.0367146 |       0.00923354 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.891 (± 1.369).
- Errore medio: RMSE = 28.063, MAE = 24.151 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.369).
- Stabilità media delle importanze tra fold: 0.033 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TR (0.160), OR (0.142), TL (0.133).

Miglior fold
- Best fold: 2 con R² = 0.460.
- Nella best fold le feature più importanti sono: TL (0.147), TR (0.140), PR (0.128).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.252 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.510 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
