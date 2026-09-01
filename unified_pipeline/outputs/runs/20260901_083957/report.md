# Instancia explicativa

## ¿Qué está haciendo este modelo?

Este modelo es un **random_forest** entrenado para **classification** sobre `target`. En el conjunto de test alcanzó una **exactitud (accuracy) de 89.5%** y un **F1 global de 0.894** (la media ponderada de precisión y recall entre las clases).

## Estas son las 15 características más importantes

Ordenadas de mayor a menor influencia, medida como importancia global:

1. **worst area** (importancia global = 0.141) — la **característica dominante**; por sí sola marca la mayor parte de la decisión del modelo.
2. **worst perimeter** (importancia global = 0.140) — entre las tres de mayor peso en las predicciones.
3. **worst concave points** (importancia global = 0.124) — entre las tres de mayor peso en las predicciones.
4. **worst radius** (importancia global = 0.083)
5. **mean concave points** (importancia global = 0.080)
6. **mean radius** (importancia global = 0.070)
7. **mean perimeter** (importancia global = 0.053)
8. **mean area** (importancia global = 0.044)
9. **mean concavity** (importancia global = 0.040)
10. **worst concavity** (importancia global = 0.037)
11. **area error** (importancia global = 0.021)
12. **worst compactness** (importancia global = 0.019)
13. **worst texture** (importancia global = 0.016)
14. **worst smoothness** (importancia global = 0.016)
15. **mean compactness** (importancia global = 0.016)

En resumen: si solo hubiera que mirar una variable, sería **worst area**. El resto del ranking ayuda a entender qué otras señales complementan esa decisión.

## ¿Por qué el modelo predijo lo que predijo?

### Muestra (index 102)
El modelo predijo la clase **1**.
Asignó una probabilidad del **98.7%** a esa clase.
¿Por qué? los factores que más la empujaron hacia arriba fueron **-0.69 < worst perimeter <= -0.28** (+0.0767), **-0.64 < worst area <= -0.35** (+0.0765), **-0.75 < worst concave points <= -0.26** (+0.0613); los que más la empujaron hacia abajo fueron **worst texture > 0.58** (-0.0397).

### Muestra (index 17)
El modelo predijo la clase **0**.
Asignó una probabilidad del **100.0%** a esa clase.
¿Por qué? los que más la empujaron hacia abajo fueron **worst area > 0.38** (-0.1391), **worst concave points > 0.78** (-0.1317), **worst perimeter > 0.56** (-0.1283).

### Muestra (index 370)
El modelo predijo la clase **0**.
Asignó una probabilidad del **99.7%** a esa clase.
¿Por qué? los que más la empujaron hacia abajo fueron **worst area > 0.38** (-0.1396), **worst concave points > 0.78** (-0.1356), **worst perimeter > 0.56** (-0.1264).

## Detalle técnico — Muestra (index 102)
- True: 1 | Pred: 1
- Probabilidades: {'0': 0.0133, '1': 0.9867}
- Top features LIME:
    - -0.69 < worst perimeter <= -0.28 -> 0.0767
    - -0.64 < worst area <= -0.35 -> 0.0765
    - -0.75 < worst concave points <= -0.26 -> 0.0613
    - -0.66 < worst radius <= -0.28 -> 0.0527
    - worst texture > 0.58 -> -0.0397
    - mean concave points <= -0.73 -> 0.0293
    - area error <= -0.60 -> 0.0285
    - worst smoothness <= -0.75 -> 0.0254
    - -0.69 < mean area <= -0.31 -> 0.0217
    - mean concavity <= -0.74 -> 0.0194

## Detalle técnico — Muestra (index 17)
- True: 0 | Pred: 0
- Probabilidades: {'0': 1.0, '1': 0.0}
- Top features LIME:
    - worst area > 0.38 -> -0.1391
    - worst concave points > 0.78 -> -0.1317
    - worst perimeter > 0.56 -> -0.1283
    - worst radius > 0.52 -> -0.1008
    - area error > 0.20 -> -0.0566
    - mean area > 0.37 -> -0.0549
    - mean radius > 0.48 -> -0.0487
    - mean concave points > 0.67 -> -0.0481
    - worst texture > 0.58 -> -0.0434
    - worst concavity > 0.48 -> -0.0430

## Detalle técnico — Muestra (index 370)
- True: 0 | Pred: 0
- Probabilidades: {'0': 0.9967, '1': 0.0033}
- Top features LIME:
    - worst area > 0.38 -> -0.1396
    - worst concave points > 0.78 -> -0.1356
    - worst perimeter > 0.56 -> -0.1264
    - worst radius > 0.52 -> -0.0992
    - area error > 0.20 -> -0.0539
    - mean area > 0.37 -> -0.0519
    - mean radius > 0.48 -> -0.0460
    - worst concavity > 0.48 -> -0.0453
    - mean concave points > 0.67 -> -0.0443
    - worst texture > 0.58 -> -0.0383
