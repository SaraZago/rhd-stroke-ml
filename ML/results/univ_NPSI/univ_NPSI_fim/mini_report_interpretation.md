# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |          R2 |     MSE |    RMSE |     MAE |
|-------:|------------:|--------:|--------:|--------:|
|      1 |  -0.190561  | 365.818 | 19.1264 | 16.3071 |
|      2 |   0.0385303 | 111.424 | 10.5557 | 10.1783 |
|      3 | -13.7522    | 322.91  | 17.9697 | 16.975  |
|      4 |  -0.433798  | 253.663 | 15.9268 | 14.4683 |
|      5 |  -0.393641  | 423.396 | 20.5766 | 18.4917 |

## Importanze (media ± std)

| feature    |   mean_importance |   std_importance |
|:-----------|------------------:|-----------------:|
| criq       |         0.175249  |        0.0645211 |
| semantic   |         0.146183  |        0.061637  |
| reyword    |         0.111403  |        0.0559536 |
| reyfig     |         0.103459  |        0.0111507 |
| denomdescr |         0.0940798 |        0.0451446 |
| trog       |         0.0935443 |        0.0394704 |
| phonemic   |         0.0849156 |        0.0311892 |
| span_back  |         0.0689869 |        0.0242487 |
| mmse       |         0.0622095 |        0.0318557 |
| span_for   |         0.0599696 |        0.0331309 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -2.946 (± 6.044).
- Errore medio: RMSE = 16.831, MAE = 15.284 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 6.044).
- Stabilità media delle importanze tra fold: 0.040 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: criq (0.175), semantic (0.146), reyword (0.111).

Miglior fold
- Best fold: 2 con R² = 0.039.
- Nella best fold le feature più importanti sono: semantic (0.219), criq (0.153), phonemic (0.127).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.155 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.800 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
