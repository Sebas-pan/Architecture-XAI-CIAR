# Instancia explicativa

## ¿Qué está haciendo este modelo?

Este modelo es un **random_forest** entrenado para **regression** sobre `SalePrice`. En el conjunto de test alcanzó un **R² de 0.891**, lo que significa que el modelo explica el 89.1% de la variabilidad del objetivo. El error típico de sus predicciones (RMSE) es de **29164.76**.

## Estas son las 15 características más importantes

Ordenadas de mayor a menor influencia, medida como contribución media (mean |SHAP|):

1. **OverallQual** (contribución media (mean |SHAP|) = 33484.790) — la **característica dominante**; por sí sola marca la mayor parte de la decisión del modelo.
2. **GrLivArea** (contribución media (mean |SHAP|) = 15593.728) — entre las tres de mayor peso en las predicciones.
3. **TotalBsmtSF** (contribución media (mean |SHAP|) = 4839.147) — entre las tres de mayor peso en las predicciones.
4. **BsmtFinSF1** (contribución media (mean |SHAP|) = 3860.299)
5. **GarageArea** (contribución media (mean |SHAP|) = 2686.684)
6. **GarageFinish_Unf** (contribución media (mean |SHAP|) = 2423.090)
7. **GarageCars** (contribución media (mean |SHAP|) = 2358.913)
8. **1stFlrSF** (contribución media (mean |SHAP|) = 2239.447)
9. **LotArea** (contribución media (mean |SHAP|) = 2139.034)
10. **YearBuilt** (contribución media (mean |SHAP|) = 2049.374)
11. **2ndFlrSF** (contribución media (mean |SHAP|) = 1590.049)
12. **YearRemodAdd** (contribución media (mean |SHAP|) = 1541.059)
13. **Fireplaces** (contribución media (mean |SHAP|) = 1411.606)
14. **BsmtQual_Ex** (contribución media (mean |SHAP|) = 1251.522)
15. **OverallCond** (contribución media (mean |SHAP|) = 881.958)

En resumen: si solo hubiera que mirar una variable, sería **OverallQual**. El resto del ranking ayuda a entender qué otras señales complementan esa decisión.

## ¿Por qué el modelo predijo lo que predijo?

### Muestra (index 1226)
El valor real era **214000.00** y el modelo predijo **204239.22** (un error de 9760.78, ≈4.6% por debajo del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **GrLivArea** (+22305), **GarageFinish_Unf** (+4308), **LotArea** (+3770); los que más la empujaron hacia abajo fueron **OverallQual** (-19440), **BsmtFinSF1** (-5623).

### Muestra (index 44)
El valor real era **141000.00** y el modelo predijo **137670.88** (un error de 3329.12, ≈2.4% por debajo del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **TotalBsmtSF** (+5611), **GarageFinish_Unf** (+2306); los que más la empujaron hacia abajo fueron **OverallQual** (-27398), **GrLivArea** (-11888), **GarageCars** (-2729).

### Muestra (index 179)
El valor real era **100000.00** y el modelo predijo **122216.07** (un error de 22216.07, ≈22.2% por encima del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **YearRemodAdd** (+2549); los que más la empujaron hacia abajo fueron **OverallQual** (-28449), **GrLivArea** (-14114), **YearBuilt** (-4393).

## Detalle técnico — Muestra (index 1226)
- True: 214000.0 | Pred: 204239.22
- Top features LIME:
    - BsmtCond_Po <= 0.00 -> -40906.9489
    - HeatingQC_Po <= 0.00 -> -40058.3660
    - GrLivArea > 0.50 -> 37964.5686
    - MiscFeature_TenC <= 0.00 -> 30605.5025
    - Utilities_NoSeWa <= 0.00 -> 26682.5894
    - GarageQual_Po <= 0.00 -> 26436.8059
    - Exterior2nd_AsphShn <= 0.00 -> 20435.0607
    - SaleType_ConLw <= 0.00 -> 17206.8827
    - SaleType_ConLI <= 0.00 -> 14454.5958
    - Condition2_RRAe <= 0.00 -> 10818.0207
- Top SHAP:
    - GrLivArea -> 22304.5472
    - OverallQual -> -19440.0835
    - BsmtFinSF1 -> -5622.5012
    - GarageFinish_Unf -> 4308.1204
    - LotArea -> 3770.1511
    - GarageCars -> 3623.0264
    - YearBuilt -> 3198.8695
    - 2ndFlrSF -> 3194.1046

## Detalle técnico — Muestra (index 44)
- True: 141000.0 | Pred: 137670.875
- Top features LIME:
    - OverallQual <= -0.82 -> -37344.2355
    - Exterior1st_AsphShn <= 0.00 -> 30849.8684
    - Utilities_NoSeWa <= 0.00 -> 27056.3863
    - SaleType_ConLI <= 0.00 -> 26348.6339
    - RoofMatl_WdShngl <= 0.00 -> -22370.8494
    - SaleType_Oth <= 0.00 -> -22329.4227
    - Condition2_RRAn <= 0.00 -> 21900.2326
    - -0.73 < GrLivArea <= -0.10 -> -20792.7128
    - Condition2_Artery <= 0.00 -> -20188.1401
    - Condition2_RRAe <= 0.00 -> 16986.7634
- Top SHAP:
    - OverallQual -> -27398.3005
    - GrLivArea -> -11887.6141
    - TotalBsmtSF -> 5611.1027
    - GarageCars -> -2729.0972
    - GarageFinish_Unf -> 2305.5902
    - BsmtFinSF1 -> -2280.1959
    - GarageArea -> -1986.9276
    - YearRemodAdd -> -1780.4998

## Detalle técnico — Muestra (index 179)
- True: 100000.0 | Pred: 122216.07
- Top features LIME:
    - OverallQual <= -0.82 -> -37139.0179
    - GrLivArea <= -0.73 -> -29503.2936
    - Neighborhood_Blueste <= 0.00 -> -25778.2100
    - MiscFeature_Gar2 <= 0.00 -> 24901.8010
    - SaleType_ConLD <= 0.00 -> -16050.5584
    - ExterCond_Po <= 0.00 -> 14628.5356
    - Exterior2nd_Other <= 0.00 -> 13914.4227
    - Condition2_RRAe <= 0.00 -> -11322.3015
    - MiscFeature_TenC <= 0.00 -> 10779.7019
    - RoofMatl_ClyTile <= 0.00 -> 5691.9061
- Top SHAP:
    - OverallQual -> -28448.8215
    - GrLivArea -> -14113.9907
    - YearBuilt -> -4393.4368
    - BsmtFinSF1 -> -3828.1520
    - YearRemodAdd -> 2548.5773
    - GarageFinish_Unf -> -1732.1455
    - 1stFlrSF -> -1501.1966
    - Fireplaces -> -1255.0649
