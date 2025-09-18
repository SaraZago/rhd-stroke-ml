# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |      MAE |
|-------:|-----------:|---------:|--------:|---------:|
|      1 | -0.5648    | 1189.57  | 34.4901 | 27.4571  |
|      2 |  0.525024  |  101.592 | 10.0793 |  6.50833 |
|      3 | -3.29713   |  417.777 | 20.4396 | 18.5667  |
|      4 | -1.3422    |  234.22  | 15.3043 | 12.9583  |
|      5 |  0.0591129 |  760.55  | 27.5781 | 23.9917  |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| PR        |         0.173246  |       0.0477673  |
| TR        |         0.153146  |       0.0417982  |
| OL        |         0.105496  |       0.0319988  |
| CL        |         0.101965  |       0.0213251  |
| OR        |         0.101512  |       0.0148651  |
| PL        |         0.0777286 |       0.0234944  |
| FL        |         0.0773596 |       0.039986   |
| TL        |         0.0760123 |       0.0192007  |
| CR        |         0.0716339 |       0.00765959 |
| FR        |         0.0618998 |       0.0298665  |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.924 (± 1.500).
- Errore medio: RMSE = 21.578, MAE = 17.896 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 1.500).
- Stabilità media delle importanze tra fold: 0.028 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: PR (0.173), TR (0.153), OL (0.105).

Miglior fold
- Best fold: 2 con R² = 0.525.
- Nella best fold le feature più importanti sono: PR (0.187), TR (0.147), OL (0.098).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: 0.158 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.256 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
