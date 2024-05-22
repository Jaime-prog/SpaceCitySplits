Segmentación de Imágenes urbanas
---
Este README proporciona una descripción detallada del proyecto de segmentación semántica de imágenes. El proyecto se basa en el uso de un conjunto de datos de segmentación semántica de imágenes urbanas llamado "Cityscapes Image Pairs".

- El conjunto de datos se puede consultar a través de la plataforma de kaggle en la siguiente liga: [_Cityscapes Image Pairs Dataset_](https://www.kaggle.com/datasets/dansbecker/cityscapes-image-pairs/data).
- El jupyternotebook se encuentra en la siguiente liga: [_Image_Segmentation.ipynb_](https://colab.research.google.com/drive/1Pfqk_PoN-YN1KyA3a5ZTAgudswapfH6P?usp=sharing)
- Se ha creado un proyecto de Google Colab además de las carpetas necesarias en la siguiente [_Ubicación_](https://drive.google.com/drive/folders/1m7DZ6JIDJk5MSV1IQJvLZ2E4pBZJO__X?usp=sharing)


## :arrow_right: Contenido del repositorio 

 _Archivos/Scripts_: 
- `Image_Segmentation_City.ipynb` 

## Dataset :information_source:

**Nombre del dataset**: Cityscapes Image Pairs

**Variables**: Las imágenes del conjunto de datos tienen un formato de 256x512 píxeles y 3 canales (RGB). El conjunto de datos está dividido en directorios de entrenamiento y validación. Este conjunto de datos comprende imágenes urbanas con etiquetas de segmentación semántica.

Inicialmente esta es la distribución de las carpetas:

- _Train_: **2975** imágenes de entrenamiento
- Test: **500** imágenes de validación

Las imágenes muestran la segmentación semántica junto con la imagen original, lo que lo convierte en un conjunto de datos valioso para tareas de segmentación semántica en entornos urbanos.

## Objetivo :dart:
El objetivo principal de este proyecto es desarrollar segmentación semántica de imágenes urbanas. La cual tiene aplicaciones en la identificación y delimitación de objetos en entornos urbanos, lo que es fundamental para diversas aplicaciones como la conducción autónoma, la planificación urbana y la vigilancia.

Desarrollar un modelo preciso de segmentación semántica de imágenes urbanas mediante deep learning representa una contribución significativa para la investigación en visión por computadora y sus aplicaciones prácticas en entornos urbanos.

## :bookmark_tabs: Justificación y respaldo en la literatura
Para la resolución de este problema, en cuánto a la metodología y a la utilización de ciertas funciones se basaron en los resultados del siguiente paper 
[Deep Semantic Segmentation of Angiogenesis Images
](https://www.mdpi.com/1422-0067/24/2/1102)

## Resultados y Evaluación Inicial :chart:

El modelo de segmentación semántica fue entrenado y evaluado en el conjunto de datos "Cityscapes Image Pairs". A continuación, presentamos los resultados obtenidos:



## Resultados y Evaluación al mejorar el modelo :writing_hand:


## Conclusiones :triangular_flag_on_post:



## :small_blue_diamond: Uso

Para utilizar estos scripts, siga estos pasos generales:

1. Clona este repositorio en tu entorno local:

   ```bash
   git clone https://github.com/Jaime-prog/SpaceCitySplits.git
   ```
2. Modifique los scripts según sea necesario para adaptarlos a su equipo específico. Por ejemplo, la ubicación de los archivos.
3. Ejecute los scripts deseados desde la línea de comandos, utilizando Python para los scripts Python y bash para el script shell.
  
   ```
    EvaluateModel.ipynb
   ```
