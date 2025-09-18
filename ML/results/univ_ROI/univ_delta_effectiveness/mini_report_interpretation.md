# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |     MAE |
|-------:|-----------:|---------:|--------:|--------:|
|      1 |  0.0403598 |  843.279 | 29.0393 | 23.2281 |
|      2 | -0.0105037 |  499.366 | 22.3465 | 18.0172 |
|      3 | -1.26183   |  548.461 | 23.4192 | 18.5419 |
|      4 |  0.068485  |  213.156 | 14.5999 | 12.0415 |
|      5 | -0.94659   | 1664.81  | 40.802  | 32.4708 |

## Importanze (media ± std)

| feature   |   mean_importance |   std_importance |
|:----------|------------------:|-----------------:|
| TL        |         0.492653  |        0.0747836 |
| TR        |         0.102868  |        0.0351214 |
| OR        |         0.0836218 |        0.0444002 |
| PL        |         0.0630219 |        0.02417   |
| PR        |         0.0550269 |        0.0318965 |
| OL        |         0.0508186 |        0.0155876 |
| FL        |         0.0505015 |        0.0152979 |
| CL        |         0.0484282 |        0.0190083 |
| FR        |         0.0265906 |        0.0124344 |
| CR        |         0.0264689 |        0.0147742 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -0.422 (± 0.633).
- Errore medio: RMSE = 26.041, MAE = 20.860 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 0.633).
- Stabilità media delle importanze tra fold: 0.029 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: TL (0.493), TR (0.103), OR (0.084).

Miglior fold
- Best fold: 4 con R² = 0.068.
- Nella best fold le feature più importanti sono: TL (0.464), OR (0.142), PL (0.097).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.184 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: -0.069 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
