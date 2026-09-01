# Instancia explicativa

## ¿Qué está haciendo este modelo?

Utilizamos un modelo de bosque aleatorio que combina muchos árboles de decisión para predecir el precio de venta de las propiedades. Este modelo alcanza un R² de 0.891, lo que significa que explica aproximadamente el 89% de la variabilidad de los precios, con un RMSE de 29164.76 y un MAE de 17728.02. En general, las predicciones son muy precisas y confiables, estando cerca de los valores reales.

Las características más importantes son OverallQual, GrLivArea y 2ndFlrSF, que indican la calidad general, el área habitable y la superficie del segundo piso. Estas variables son clave porque el precio de una vivienda depende fuertemente de su estado y tamaño.

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
