# Reporte — Detección YOLO11

## Entrenamiento
- Modelo: `yolo11` (variante `yolov11n`)
- Dispositivo: `0` · tiempo: 3.67 min
- Clases: Cat, Dog
- EDA: `class_distribution.png`, `sample_grid.jpg` y `eda_image.json` (distribución por split, stats de tamaño)

## Métricas (test)
- mAP50: **0.7452**
- mAP50-95: **0.5756**
- Precision (mean): 0.9257
- Recall (mean): 0.7550
    - Cat · AP50=0.8950 · AP50-95=0.7282
    - Dog · AP50=0.5954 · AP50-95=0.4231

## ¿Qué está haciendo este modelo?

El modelo alcanzó un **mAP50 de 0.745** y un **mAP50-95 de 0.576** en el conjunto de test, lo que indica que detecta los objetos con buena precisión.
La clase mejor detectada es **Cat** (AP50 = 0.895)
y la más difícil es **Dog** (AP50 = 0.595).

En `C:\Users\Fabrizio\Desktop\CIAR\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.jpg` el modelo **no encontró ninguna detección** por encima del umbral de confianza.
En `C:\Users\Fabrizio\Desktop\CIAR\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.jpg` el modelo detectó **1× Cat** con una confianza media de **94%**.
El mapa de calor **Grad-CAM** señala las regiones de la imagen que más respaldan la clase detectada (Cat).
En `C:\Users\Fabrizio\Desktop\CIAR\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_170_jpg.rf.rgEfrCyIhPrJGznb5SJ8.jpg` el modelo detectó **1× Cat** con una confianza media de **92%**.
El mapa de calor **Grad-CAM** señala las regiones de la imagen que más respaldan la clase detectada (Cat).
En `C:\Users\Fabrizio\Desktop\CIAR\unified_pipeline\data\CatsDogs_YOLO11\test\images\cat_208_jpg.rf.lXeTKCfgfVEp2CUm37CX.jpg` el modelo detectó **1× Cat** con una confianza media de **90%**.
El mapa de calor **Grad-CAM** señala las regiones de la imagen que más respaldan la clase detectada (Cat).

## Predicciones de ejemplo (`predictions/`)
- `cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.jpg` → 0 detecciones
- `cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.jpg` → 1 detecciones
    - Cat (0.94) bbox [324.5, 7.9, 670.0, 351.8]
- `cat_170_jpg.rf.rgEfrCyIhPrJGznb5SJ8.jpg` → 1 detecciones
    - Cat (0.92) bbox [305.3, 37.7, 966.4, 703.1]
- `cat_208_jpg.rf.lXeTKCfgfVEp2CUm37CX.jpg` → 1 detecciones
    - Cat (0.90) bbox [39.5, 5.9, 246.1, 217.3]

## Explicabilidad (`xai/`)

### GRADCAM
Artefactos:
- `gradcam_cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.png` (clase objetivo: Cat)
- `gradcam_cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.png` (clase objetivo: Cat)
- `gradcam_cat_170_jpg.rf.rgEfrCyIhPrJGznb5SJ8.png` (clase objetivo: Cat)
- `gradcam_cat_208_jpg.rf.lXeTKCfgfVEp2CUm37CX.png` (clase objetivo: Cat)

### OCCLUSION
Artefactos:
- `occlusion_cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.png` (clase objetivo: None)
- `occlusion_cat_170_jpg.rf.rgEfrCyIhPrJGznb5SJ8.png` (clase objetivo: None)
- `occlusion_cat_208_jpg.rf.lXeTKCfgfVEp2CUm37CX.png` (clase objetivo: None)

### LIME_IMAGE
Artefactos:
- `lime_image_cat_111_jpg.rf.XSCmTLQPKBr7ZNZzXhm0.png` (clase objetivo: Cat)
- `lime_image_cat_14_jpg.rf.2aEiCGe3AlOrkQg6hHz8.png` (clase objetivo: Cat)
- `lime_image_cat_170_jpg.rf.rgEfrCyIhPrJGznb5SJ8.png` (clase objetivo: Cat)
- `lime_image_cat_208_jpg.rf.lXeTKCfgfVEp2CUm37CX.png` (clase objetivo: Cat)

## Cómo interpretar los mapas
- **Grad-CAM**: mapa de calor sobre la última conv de la rama de clases.
    Las zonas rojas muestran qué regiones **soportan** la clase detectada.
- **Occlusion Sensitivity**: celda en gris → caída de confianza de la caja.
    Celdas rojas = la confianza Depende de esa zona.
- **LIME Image**: superpíxeles que, al ocultarse, aumentaron la clase objetivo
    (verde) o la disminuyeron (rojo). Se agrega la confianza por clase como
    "probabilidad" para el clasificador LIME.

Artículo de referencia: métricas en `metrics.json`, predicciones en `predictions/predictions.json`, detalle XAI en `xai/*.json` y mapas `.npy`.