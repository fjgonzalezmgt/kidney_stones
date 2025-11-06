# YOLOv8 – Detección de Cálculos Renales en Imágenes Médicas

Este proyecto implementa un flujo completo de detección de **cálculos renales** en imágenes endoscópicas utilizando **YOLOv8**, una arquitectura de detección de objetos en tiempo real.  

Permite entrenar el modelo, evaluarlo con métricas estándar, ajustar umbrales para mejorar su desempeño y generar predicciones que visualizan y delimitan automáticamente la ubicación de los cálculos.

---

## 📌 Desarrollado por

**Autor:** [Francisco González](https://www.linkedin.com/in/franciscogonzalez/)  
**Especialización:** Ingeniería Industrial, análisis de datos, visión por computadora aplicada a control de calidad y apoyo clínico.

---

## 📂 Dataset

Este proyecto utiliza el dataset **Kidney Stone Images** disponible en Kaggle, conformado por imágenes procedentes de procedimientos médicos como endoscopías o litotricias.  

- **Fuente oficial:** [Kidney Stone Images Dataset - Kaggle](https://www.kaggle.com/datasets/safurahajiheidari/kidney-stone-images)  
- **Clases incluidas:**  
  | Class ID | Nombre     | Descripción                 |
  |----------|------------|-----------------------------|
  | 0        | `Tas_Var`  | Cálculo / Piedra renal visible |

- Los datos han sido divididos en:
```

train/  -> Entrenamiento del modelo
test/   -> Evaluación final del desempeño

```

- Las etiquetas `/labels/*.txt` están en formato YOLO:
```

<class_id> <x_center> <y_center> <width> <height>

````

---

## 🚀 Modelo utilizado: YOLOv8

**YOLO (You Only Look Once)** es una familia de redes neuronales especializadas en la detección de objetos en una sola pasada, lo que permite obtener predicciones inmediatamente, incluso en tiempo real.

Este proyecto usa **Ultralytics YOLOv8**, destacando por:
- Alto rendimiento y eficiencia
- Facilidad de uso vía Python o CLI
- Soporte para entrenamiento, validación, exportación y despliegue
- Métricas integradas como `mAP`, `precision`, `recall`
- Configuración modular (diferentes tamaños de red: nano, small, medium, etc.)

---

## 🧠 Objetivo

Entrenar un modelo YOLOv8 capaz de detectar de forma automática y precisa la presencia de cálculos renales en imágenes médicas, con énfasis en:

- Alta precisión (minimizar falsos positivos)
- Desempeño clínicamente útil
- Uso potencial en sistemas de apoyo a diagnósticos o análisis automatizados

---

## 📊 Resultados principales (modelo `yolov8s_kidney_img768`)

| Métrica        | Valor |
|----------------|-------|
| Precision      | 0.8736 |
| Recall         | 0.6786 |
| mAP50          | 0.7779 |
| mAP50-95       | 0.3717 |
| Umbral usado   | `conf=0.40, iou=0.55` |

> **Interpretación general:** El modelo detecta de forma confiable cuando hay una piedra, aunque todavía hay margen de mejora en la cobertura total y precisión del bounding box.

---

## 📘 Contenido del Notebook

El notebook incluido en este proyecto guía paso a paso:

1. Preparación y exploración del dataset  
2. Configuración de YOLOv8  
3. Entrenamiento con augmentations y EarlyStopping  
4. Validación del modelo y análisis de métricas  
5. Ajuste de hyperparámetros (`conf`, `iou`)  
6. Generación de matriz de confusión y gráficos  
7. Exportación de predicciones y resultados consolidados  

---

## 🔧 Requisitos (Colab o local)

- `python >= 3.8`
- `ultralytics`
- `torch` con CUDA (opcional pero recomendado)
- Entorno preparado con GPU para entrenamiento

Instalación rápida:

```bash
pip install ultralytics
````

---

## 📄 Licencia

Este proyecto sigue la licencia del dataset original y del framework Ultralytics YOLO.
Ver términos oficiales según corresponda al uso en producción o contexto médico.

---

## 🧩 Próximas mejoras

* Incorporar múltiples clases (ej. diferentes tipos de cálculos o tejido sano)
* Optimización del modelo para dispositivos embebidos
* Integración con pipelines clínicos o visualización web
* Comparación con otros frameworks (Detectron2, EfficientDet, etc.)

---

¿Comentarios o sugerencias? Puedes contactarme vía LinkedIn o contribuir al código.
Gracias por revisar este proyecto.
