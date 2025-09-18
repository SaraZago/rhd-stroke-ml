# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |      MAE |
|-------:|-----------:|---------:|--------:|---------:|
|      1 | -0.720691  | 1308.08  | 36.1673 | 26.8214  |
|      2 |  0.503085  |  106.285 | 10.3094 |  7.24167 |
|      3 | -6.1371    |  693.885 | 26.3417 | 22.9333  |
|      4 | -1.63039   |  263.039 | 16.2185 | 14.0417  |
|      5 | -0.0761572 |  869.894 | 29.494  | 23.375   |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| OR        |         0.147981  |        0.0253663 |
| TL        |         0.141666  |        0.0266028 |
| TR        |         0.135179  |        0.0431216 |
| PL        |         0.112508  |        0.0353054 |
| PR        |         0.101191  |        0.0534555 |
| CR        |         0.0883898 |        0.0141256 |
| FR        |         0.0727362 |        0.0153001 |
| FL        |         0.0701862 |        0.0224671 |
| CL        |         0.0662003 |        0.0117533 |
| OL        |         0.0639628 |        0.0201996 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.612 (± 2.651).
- Errore medio: RMSE = 23.706, MAE = 18.883 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 2.651).
- Stabilità media delle importanze tra fold: 0.027 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: OR (0.148), TL (0.142), TR (0.135).

Miglior fold
- Best fold: 2 con R² = 0.503.
- Nella best fold le feature più importanti sono: PL (0.167), OR (0.161), TL (0.141).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.292 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.360 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
