# SpaceCitySplits (Image Segmentation)
---
Este README proporciona una descripción detallada del proyecto de segmentación semántica de imágenes. El proyecto se basa en el uso de un conjunto de datos de segmentación semántica de imágenes urbanas llamado "Cityscapes Image Pairs".

Al cual se puede acceder a través de la siguiente liga: [Cityscapes Image Pairs Dataset](https://www.kaggle.com/datasets/dansbecker/cityscapes-image-pairs/data).

A continuación, se presenta una estructura que detalla los aspectos clave de este proyecto.

## :arrow_right: Contenido del repositorio 

 _Archivos/Scripts_: 
- `Semantic_Segmentation_Model.ipynb` (Implementación modelo base)
-  `Improved_Semantic_Model.ipynb` (Implementación modelo mejorado)
- `EvaluateModel.ipynb` (Libreta para evaluar el modelo)
- `Reporte Implementación de un modelo de segmentación semántica` 

## Dataset :information_source:

**Nombre del dataset**: Cityscapes Image Pairs

**Variables**: Las imágenes del conjunto de datos tienen un formato de 256x512 píxeles y 3 canales (RGB). El conjunto de datos está dividido en directorios de entrenamiento y validación. Este conjunto de datos comprende imágenes urbanas con etiquetas de segmentación semántica, ideales para tareas de segmentación semántica.

Inicialmente esta es la distribución de las carpetas:

- _Train_: **2975** imágenes de entrenamiento
- _Validation_: **500** imágenes de validación

Las imágenes muestran la segmentación semántica junto con la imagen original, lo que lo convierte en un conjunto de datos valioso para tareas de segmentación semántica en entornos urbanos.

## Objetivo :dart:
El objetivo principal de este proyecto es desarrollar 
La segmentación semántica de imágenes urbanas tiene aplicaciones en la identificación y delimitación de objetos en entornos urbanos, lo que es fundamental para diversas aplicaciones como la conducción autónoma, la planificación urbana y la vigilancia.

Desarrollar un modelo preciso de segmentación semántica de imágenes urbanas mediante deep learning representa una contribución significativa para la investigación en visión por computadora y sus aplicaciones prácticas en entornos urbanos.

## Resultados y Evaluación Inicial :chart:

El modelo de segmentación semántica fue entrenado y evaluado en el conjunto de datos "Cityscapes Image Pairs". A continuación, presentamos los resultados obtenidos:



## Resultados y Evaluación al mejorar el modelo :writing_hand:


## Conclusiones :triangular_flag_on_post:

En conclusión, el proyecto de segmentación semántica de imágenes urbanas ha logrado desarrollar un modelo de CNN capaz de segmentar objetos en entornos urbanos con alta precisión. Sin embargo, se observa margen para seguir mejorando el modelo, lo que podría lograrse mediante la optimización de hiperparámetros y la exploración de arquitecturas de redes neuronales más avanzadas. Además, se debe considerar la diversidad y complejidad de las imágenes urbanas para futuros trabajos.

## :small_blue_diamond: Uso

Para utilizar estos scripts, siga estos pasos generales:

1. Clona este repositorio en tu entorno local:

   ```bash
   git clone https://github.com/TuUsuario/AI_ImageSegmentation_SemanticSight.git
   ```
2. Modifique los scripts según sea necesario para adaptarlos a su equipo específico. Por ejemplo, la ubicación de los archivos.
3. Ejecute los scripts deseados desde la línea de comandos, utilizando Python para los scripts Python y bash para el script shell.
  
   ```
    EvaluateModel.ipynb
   ```
