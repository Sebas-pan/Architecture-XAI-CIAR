# Instancia explicativa

## ¿Qué está haciendo este modelo?

El bosque aleatorio clasifica el objetivo con una precisión del 89.5% y un F1 de 0.894, lo que muestra que acierta casi el 90% de las veces y equilibra bien las clases. Funciona como un conjunto de árboles de decisión que votan juntos para tomar la decisión final, lo que lo hace robusto y fácil de interpretar. Esto significa que, en la práctica, el modelo es confiable para predecir el valor del objetivo.

El modelo se basa principalmente en características como el tamaño (área, perímetro y radio) y la forma (puntos cóncavos y concavidad) de las lesiones, ya que estas son las que más influyen en su diagnóstico. Al analizar estos factores clave, el modelo puede identificar patrones relevantes y proporcionar una predicción más precisa y confiable.

## ¿Por qué el modelo predijo lo que predijo?

### Muestra (index 102)
El modelo predijo la clase **1**.
Asignó una probabilidad del **98.7%** a esa clase.
¿Por qué? los factores que más la empujaron hacia arriba fueron **worst perimeter** (+0.0597), **worst area** (+0.0585), **worst concave points** (+0.0512).

### Muestra (index 17)
El modelo predijo la clase **0**.
Asignó una probabilidad del **100.0%** a esa clase.
¿Por qué? los que más la empujaron hacia abajo fueron **worst concave points** (-0.0889), **worst perimeter** (-0.0869), **worst area** (-0.0829).

### Muestra (index 370)
El modelo predijo la clase **0**.
Asignó una probabilidad del **99.7%** a esa clase.
¿Por qué? los que más la empujaron hacia abajo fueron **worst area** (-0.0915), **worst concave points** (-0.0884), **worst perimeter** (-0.0883).

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
- Top SHAP:
    - worst perimeter -> 0.0597
    - worst area -> 0.0585
    - worst concave points -> 0.0512
    - worst radius -> 0.0389
    - mean concave points -> 0.0278
    - worst concavity -> 0.0247
    - mean concavity -> 0.0188
    - mean radius -> 0.0187

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
- Top SHAP:
    - worst concave points -> -0.0889
    - worst perimeter -> -0.0869
    - worst area -> -0.0829
    - worst radius -> -0.0555
    - mean concave points -> -0.0487
    - mean radius -> -0.0331
    - mean area -> -0.0311
    - mean perimeter -> -0.0263

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
- Top SHAP:
    - worst area -> -0.0915
    - worst concave points -> -0.0884
    - worst perimeter -> -0.0883
    - worst radius -> -0.0566
    - mean concave points -> -0.0488
    - mean radius -> -0.0347
    - mean area -> -0.0322
    - worst concavity -> -0.0286
