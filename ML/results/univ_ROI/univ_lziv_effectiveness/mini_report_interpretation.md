# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |        R2 |      MSE |    RMSE |     MAE |
|-------:|----------:|---------:|--------:|--------:|
|      1 | -0.540866 | 1354.03  | 36.7971 | 29.7979 |
|      2 |  0.619256 |  188.154 | 13.7169 | 11.8027 |
|      3 | -0.537721 |  372.875 | 19.31   | 16.7301 |
|      4 | -1.18905  |  500.915 | 22.3811 | 19.5506 |
|      5 | -0.377651 | 1178.23  | 34.3253 | 30.8003 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PR        |         0.199612  |       0.0741458  |
| TL        |         0.180765  |       0.0773594  |
| PL        |         0.160525  |       0.128048   |
| CL        |         0.0962062 |       0.0429631  |
| FR        |         0.0799674 |       0.0390204  |
| FL        |         0.0665001 |       0.0145945  |
| OL        |         0.0650026 |       0.0437657  |
| OR        |         0.0549595 |       0.00465261 |
| TR        |         0.0484235 |       0.0124629  |
| CR        |         0.0480384 |       0.0181497  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.405 (± 0.652).
- Errore medio: RMSE = 25.306, MAE = 21.736 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 0.652).
- Stabilità media delle importanze tra fold: 0.046 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PR (0.200), TL (0.181), PL (0.161).

Miglior fold
- Best fold: 2 con R² = 0.619.
- Nella best fold le feature più importanti sono: TL (0.277), PR (0.172), CL (0.127).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.789 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.710 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
