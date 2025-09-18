# Mini-report automatico: risultati CV e interpretazione

## Metriche per fold

|   Fold |         R2 |      MSE |    RMSE |     MAE |
|-------:|-----------:|---------:|--------:|--------:|
|      1 | -0.593396  | 1211.31  | 34.8038 | 28.4929 |
|      2 | -0.0809195 |  231.197 | 15.2052 | 13.2833 |
|      3 | -7.86436   |  861.813 | 29.3567 | 28.2417 |
|      4 | -6.92862   |  792.862 | 28.1578 | 24.1583 |
|      5 | -0.404302  | 1135.14  | 33.6919 | 28.05   |

## Importanze (media ± std)

| feature    |   mean_importance |   std_importance |
|:-----------|------------------:|-----------------:|
| semantic   |         0.223739  |        0.109927  |
| criq       |         0.121364  |        0.0558868 |
| reyword    |         0.115483  |        0.0782927 |
| denomdescr |         0.0944177 |        0.0861202 |
| span_back  |         0.0937495 |        0.0348304 |
| reyfig     |         0.0936545 |        0.0174291 |
| mmse       |         0.0765353 |        0.048916  |
| phonemic   |         0.0707536 |        0.0244669 |
| span_for   |         0.0657449 |        0.0227101 |
| trog       |         0.0445586 |        0.0203143 |

## Interpretazione automatica

Performance complessiva
- Media R² sui fold: -3.174 (± 3.873).
- Errore medio: RMSE = 28.243, MAE = 24.445 (stessa unità della variabile target).

Stabilità del modello
- La variabilità del R² tra i fold è alta (std = 3.873).
- Stabilità media delle importanze tra fold: 0.050 (più basso = più stabile).

Feature più importanti (media su tutti i fold)
- Top-3: semantic (0.224), criq (0.121), reyword (0.115).

Miglior fold
- Best fold: 2 con R² = -0.081.
- Nella best fold le feature più importanti sono: semantic (0.276), span_back (0.128), reyword (0.121).

Analisi dei residui (best fold)
- Correlazione residui–predizioni: -0.371 (0 ≈ assenza di bias lineare).
- Correlazione |residui|–predizioni: 0.376 (valori positivi indicano possibile eteroschedasticità).
- Outlier (|res| > 3·std): 0.
