# Instancia explicativa

## ¿Qué está haciendo este modelo?

Este modelo es un **random_forest** entrenado para **regression** sobre `SalePrice`. En el conjunto de test alcanzó un **R² de 0.891**, lo que significa que el modelo explica el 89.1% de la variabilidad del objetivo. El error típico de sus predicciones (RMSE) es de **29164.76**.

## Estas son las 15 características más importantes

Ordenadas de mayor a menor influencia, medida como importancia global:

1. **OverallQual** (importancia global = 0.542) — la **característica dominante**; por sí sola marca la mayor parte de la decisión del modelo.
2. **GrLivArea** (importancia global = 0.122) — entre las tres de mayor peso en las predicciones.
3. **2ndFlrSF** (importancia global = 0.033) — entre las tres de mayor peso en las predicciones.
4. **TotalBsmtSF** (importancia global = 0.030)
5. **BsmtFinSF1** (importancia global = 0.026)
6. **1stFlrSF** (importancia global = 0.025)
7. **GarageCars** (importancia global = 0.020)
8. **GarageArea** (importancia global = 0.017)
9. **LotArea** (importancia global = 0.015)
10. **BsmtQual_Ex** (importancia global = 0.013)
11. **YearBuilt** (importancia global = 0.011)
12. **GarageFinish_Unf** (importancia global = 0.010)
13. **LotFrontage** (importancia global = 0.007)
14. **YearRemodAdd** (importancia global = 0.007)
15. **TotRmsAbvGrd** (importancia global = 0.006)

En resumen: si solo hubiera que mirar una variable, sería **OverallQual**. El resto del ranking ayuda a entender qué otras señales complementan esa decisión.

## ¿Por qué el modelo predijo lo que predijo?

### Muestra (index 1226)
El valor real era **214000.00** y el modelo predijo **204239.22** (un error de 9760.78, ≈4.6% por debajo del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **GrLivArea > 0.50** (+37,965), **MiscFeature_TenC <= 0.00** (+30,606), **Utilities_NoSeWa <= 0.00** (+26,683); los que más la empujaron hacia abajo fueron **BsmtCond_Po <= 0.00** (-40,907), **HeatingQC_Po <= 0.00** (-40,058).

### Muestra (index 44)
El valor real era **141000.00** y el modelo predijo **137670.88** (un error de 3329.12, ≈2.4% por debajo del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **Exterior1st_AsphShn <= 0.00** (+30,850), **Utilities_NoSeWa <= 0.00** (+27,056), **SaleType_ConLI <= 0.00** (+26,349); los que más la empujaron hacia abajo fueron **OverallQual <= -0.82** (-37,344), **RoofMatl_WdShngl <= 0.00** (-22,371), **SaleType_Oth <= 0.00** (-22,329).

### Muestra (index 179)
El valor real era **100000.00** y el modelo predijo **122216.07** (un error de 22216.07, ≈22.2% por encima del valor real).
¿Por qué? los factores que más la empujaron hacia arriba fueron **MiscFeature_Gar2 <= 0.00** (+24,902), **ExterCond_Po <= 0.00** (+14,629), **Exterior2nd_Other <= 0.00** (+13,914); los que más la empujaron hacia abajo fueron **OverallQual <= -0.82** (-37,139), **GrLivArea <= -0.73** (-29,503), **Neighborhood_Blueste <= 0.00** (-25,778).

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
