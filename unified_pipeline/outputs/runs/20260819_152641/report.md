# Reporte — Detección YOLO11

## Entrenamiento
- Modelo: `yolo11` (variante `yolov11n`)
- Dispositivo: `0` · tiempo: 0.55 min
- Clases: Cat, Dog
- EDA: `class_distribution.png`, `sample_grid.jpg` y `eda_image.json` (distribución por split, stats de tamaño)

## Métricas (test)
- mAP50: **0.0000**
- mAP50-95: **0.0000**
- Precision (mean): 0.0000
- Recall (mean): 0.0000
    - Cat · AP50=n/a · AP50-95=n/a
    - Dog · AP50=n/a · AP50-95=n/a

## ¿Qué está haciendo este modelo?

El modelo alcanzó un **mAP50 de 0.000** y un **mAP50-95 de 0.000** en el conjunto de test, lo que indica que detecta los objetos con moderada precisión.
La clase mejor detectada es **Cat** (AP50 = 0.000)
y la más difícil es **Dog** (AP50 = 0.000).

En `C:\Users\I13310\Desktop\Proyecto\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.jpg` el modelo **no encontró ninguna detección** por encima del umbral de confianza.
En `C:\Users\I13310\Desktop\Proyecto\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.jpg` el modelo **no encontró ninguna detección** por encima del umbral de confianza.

## Predicciones de ejemplo (`predictions/`)
- `cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.jpg` → 0 detecciones
- `cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.jpg` → 0 detecciones

## Explicabilidad (`xai/`)

### GRADCAM
**ERROR**: Invalid device string: '0'

### OCCLUSION
**ERROR**: Occlusion no encontró detecciones en las imágenes dadas.

### LIME_IMAGE
Artefactos:
- `lime_image_cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.png` (clase objetivo: Dog)
- `lime_image_cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.png` (clase objetivo: Dog)

## Cómo interpretar los mapas
- **Grad-CAM**: mapa de calor sobre la última conv de la rama de clases.
    Las zonas rojas muestran qué regiones **soportan** la clase detectada.
- **Occlusion Sensitivity**: celda en gris → caída de confianza de la caja.
    Celdas rojas = la confianza Depende de esa zona.
- **LIME Image**: superpíxeles que, al ocultarse, aumentaron la clase objetivo
    (verde) o la disminuyeron (rojo). Se agrega la confianza por clase como
    "probabilidad" para el clasificador LIME.

Artículo de referencia: métricas en `metrics.json`, predicciones en `predictions/predictions.json`, detalle XAI en `xai/*.json` y mapas `.npy`.