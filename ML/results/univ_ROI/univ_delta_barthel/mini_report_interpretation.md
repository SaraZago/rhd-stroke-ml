# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |     MAE |
|-------:|-----------:|---------:|--------:|--------:|
|      1 | -0.254011  |  953.304 | 30.8756 | 25.4286 |
|      2 | -0.0918032 |  233.525 | 15.2815 | 12.575  |
|      3 | -3.12671   |  401.208 | 20.0302 | 18.4917 |
|      4 | -2.42143   |  342.143 | 18.4971 | 17.525  |
|      5 | -0.468119  | 1186.73  | 34.4489 | 29.4    |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| TL        |         0.329858  |       0.0362818  |
| OR        |         0.106546  |       0.019596   |
| FR        |         0.0915906 |       0.0228447  |
| PR        |         0.0851473 |       0.0428451  |
| OL        |         0.0825601 |       0.0152544  |
| FL        |         0.0762733 |       0.0170449  |
| TR        |         0.0679811 |       0.0265869  |
| CL        |         0.0604883 |       0.0202931  |
| PL        |         0.05646   |       0.00977541 |
| CR        |         0.0430949 |       0.00649122 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -1.272 (± 1.400).
- Errore medio: RMSE = 23.827, MAE = 20.684 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.400).
- Stabilità media delle importanze tra fold: 0.022 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TL (0.330), OR (0.107), FR (0.092).

Miglior fold
- Best fold: 2 con R² = -0.092.
- Nella best fold le feature più importanti sono: TL (0.342), OR (0.105), PR (0.094).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.380 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.516 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
