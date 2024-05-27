Segmentación de Imágenes Urbanas
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

## :gear: Preprocesamiento de datos

- **Redimensionamiento**: Imágenes y máscaras se ajustaron a 192x192 píxeles para coherencia espacial.
- **Conversión de color:** Se cambió de BGR a RGB para compatibilidad con modelos de aprendizaje profundo.
- **Normalización:** Valores de píxeles se escalaron a un rango de 0 a 1 para estabilidad.
- **Partición:** Imágenes se dividieron en entrada y máscara para entrenamiento adecuado.
- **División de datos:** 2,900 muestras para entrenamiento y el resto para validación.

## :diamond_shape_with_a_dot_inside: Arquitectura del modelo
  Para este problema se decidio implementar un unet autoencoder para poder hacer la segmentación de imágenes. Para esta arquitectura contamos con 2 partes esenciales: 
  - EncoderLayerBlock
 
Esta sección de la arquitectura es la que se encarga de poder captar las características tanto de nivel bajo como de nivel alto. Algunos ejemplos de estas características de bajo nivel podrían incluir, los colores, las figuras básicas, los bordes, etc. Mientras que las características de alto nivel tienen que ver con patrones más intrínsecos dentro de la imagen. Ahora bien, en esta arquitectura en especifica se cuenta con la sección de las **capas de convolución** que son las encargadas de extraer las características antes mencionadas, y capas de max pooling que son las encargadas de reducir el espacio dimensional de la imágen. En este caso se configuro 2 capas de convolución en un kernel de 3x3 y tras esta operación se realiza el max pooling.
  - DecoderLayerBlock

Esta sección se encarga de generar la segmentación final, lo cual hace a partir de sobremuestrar 'upsampling' para poder incrementar las dimensiones espaciales del mapa de características. En este caso el tamaño del kernel es de (2,2) y el stride se configuro en (2,2) lo que resulta en aumentar en un factor de 2 espacio dimensional. El upsampling se configura con una capa de 'Conv2DTranspose' que también se conoce como deconvolution lo cual nos ayuda a reconstruir una imagen a partir de una versión comprimida (en este caso proveniente del encoder). 

Después configuramos como tal la arquitectura del unet autoencoder, en el cual se configura 4 bloques del Encoder y después se tiene una capa que procesa la versión más comprimida de la imagen con el mayor número de filtros y después se configuran otros 4 bloques de Decoder el cual progresivamente va aumentando el espacio dimensional. Y para la capa de la salida se busca generar o reconstruir la imagen de entrada entonces se utiliza la función 'sigmoid' para delimitar el output de 0 a 1 para cada uno de los pixeles normalizados. Adicionalmente, se define el 'padding:same' porque se quiere la imagen reconstruida tenga las mismas dimensiones que la imagen original o la imagen de entrada. 

## Resultados y Evaluación Inicial :chart:

El modelo de segmentación semántica fue entrenado y evaluado en el conjunto de datos "Cityscapes Image Pairs". A continuación, presentamos los resultados obtenidos:

**(Test Loss):** Un valor de 0.5688 indica que el modelo aún tiene margen para mejorar en la predicción precisa de las etiquetas de las imágenes. 
**(Test Accuracy): **Una precisión de 0.7107 sugiere que el modelo acierta en la clasificación de aproximadamente el 71% de las imágenes.
**IoU (Mean Intersection over Union):** Un IoU promedio de 0.9297 indica que el modelo predice con alta precisión la superposición entre las áreas segmentadas y las áreas reales. Un IoU cercano a 1 indica una coincidencia casi perfecta entre las segmentaciones predichas y reales.
**Coeficiente de Dice:** Para esta métrica se obtuvo un coeficiente de Dice de 0.4273. El coeficiente de Dice se enfoca en la evaluación de la coincidencia de volumen entre las segmentaciones, y un valor cercano a 1 indica una alta coincidencia de volumen.

## Resultados y Evaluación al mejorar el modelo :writing_hand:
Intersección media sobre la Unión (IoU): 0.9297
La métrica de intersección media sobre la unión (IoU) mide la superposición entre las máscaras de segmentación previstas y las máscaras reales. Una puntuación IoU de 0.9297 indica un alto nivel de concordancia entre las máscaras de segmentación predichas y las reales, con una parte significativa de la máscara predicha que se solapa con la máscara real.
Coeficiente Dice: 0.4587
El coeficiente Dice es otra métrica utilizada habitualmente para evaluar la similitud entre dos conjuntos. Un coeficiente Dice de 0.4587 indica que alrededor del 45.87% de los píxeles de la máscara predicha coinciden con los píxeles de la máscara real. Aunque este valor es inferior en comparación con el IoU, sigue indicando un nivel moderado de concordancia entre las máscaras predicha y real.


## Uso Imágenes Reales :triangular_flag_on_post:
![Screenshot output base model]([https://myoctocat.com/assets/images/base-octocat.svg](https://github.com/Jaime-prog/SpaceCitySplits/blob/main/Resoure_Images/output_base_model.png)
![Screenshot output improved model]([https://myoctocat.com/assets/images/base-octocat.svg](https://github.com/Jaime-prog/SpaceCitySplits/blob/main/Resoure_Images/output_improved_model.png)

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

---
# Referencias
- [Deep Semantic Segmentation of Angiogenesis Images
](https://www.mdpi.com/1422-0067/24/2/1102)
- [Unet Architecture](https://www.kaggle.com/code/prvnkmr/unet-architecture-breakdown)
