# Clasificación de imágenes dermatológicas por patología

## Origen del dataset

Este proyecto utiliza el dataset **PAD-UFES-20: _A skin lesion dataset composed of patient data and clinical images collected from smartphones_**.

El dataset fue publicado en **Mendeley Data** el **7 de julio de 2020**, en su **versión 1**, con el DOI:

**10.17632/zr7vgbcyr2.1**

Fuente oficial del dataset:

https://data.mendeley.com/datasets/zr7vgbcyr2/1

El conjunto de datos fue recolectado por el **Dermatological and Surgical Assistance Program — PAD**, perteneciente a la **Federal University of Espírito Santo — UFES, Brasil**. Este programa brinda atención dermatológica gratuita, especialmente a personas de bajos recursos que no pueden acceder fácilmente a tratamientos privados.

El dataset contiene imágenes clínicas de lesiones cutáneas tomadas con teléfonos inteligentes. Debido a que las imágenes fueron capturadas con diferentes dispositivos móviles, estas pueden presentar variaciones en tamaño, resolución, iluminación, enfoque y condiciones de adquisición.

Según la fuente original, el dataset contiene:

- **2.298 imágenes clínicas de lesiones cutáneas**
- **1.373 pacientes**
- **1.641 lesiones de piel**
- Imágenes en formato **PNG**
- Metadatos clínicos organizados en un archivo **CSV**
- Hasta **26 características clínicas** asociadas a cada muestra

Cada imagen está relacionada con información clínica del paciente y de la lesión, como edad, región anatómica, tipo de piel según Fitzpatrick, diámetro de la lesión y diagnóstico dermatológico.

## Clases diagnósticas del dataset

El dataset PAD-UFES-20 incluye lesiones cutáneas clasificadas en las siguientes categorías:

- **ACK**: Actinic Keratosis
- **BCC**: Basal Cell Carcinoma
- **MEL**: Melanoma
- **NEV**: Nevus
- **SCC**: Squamous Cell Carcinoma
- **SEK**: Seborrheic Keratosis

La fuente original también menciona **Bowen’s disease — BOD**. Sin embargo, esta lesión es considerada una forma de **SCC in situ**, por lo que en el dataset original fue agrupada dentro de la clase **SCC**. Por esta razón, el conjunto final se organiza en seis clases principales.

## Motivo de la separación del dataset

El dataset original se descarga con las imágenes y un archivo CSV de metadatos. En ese archivo CSV, cada imagen está identificada mediante la columna `img_id` y su diagnóstico se encuentra en la columna `diagnostic`.

Sin embargo, para entrenar modelos de clasificación de imágenes, especialmente redes neuronales convolucionales, resulta más práctico organizar las imágenes en carpetas separadas por clase. Esta estructura es común en frameworks de aprendizaje profundo como **PyTorch**, **TensorFlow** y **Keras**.

Por esta razón, en este proyecto se realizó una separación automática de las imágenes según su diagnóstico. El script de Python lee el archivo `x.csv`, toma el valor de la columna `diagnostic` y copia cada imagen a una carpeta correspondiente a su patología.

La estructura generada es la siguiente:

```text
dataset_clasificado_por_patologia/
├── ACK/
├── BCC/
├── MEL/
├── NEV/
├── SCC/
└── SEK/
Sí. Pega este bloque directamente en tu `README.md`. Los datos principales salen de la página oficial de Mendeley Data del dataset PAD-UFES-20, donde se reporta el título, DOI, origen institucional, número de imágenes, pacientes, lesiones, clases diagnósticas, licencia y aprobación ética. ([Mendeley Data][1])

````markdown
# Clasificación de imágenes dermatológicas por patología

## Origen del dataset

Este proyecto utiliza el dataset **PAD-UFES-20: _A skin lesion dataset composed of patient data and clinical images collected from smartphones_**.

El dataset fue publicado en **Mendeley Data** el **7 de julio de 2020**, en su **versión 1**, con el DOI:

**10.17632/zr7vgbcyr2.1**

Fuente oficial del dataset:

https://data.mendeley.com/datasets/zr7vgbcyr2/1

El conjunto de datos fue recolectado por el **Dermatological and Surgical Assistance Program — PAD**, perteneciente a la **Federal University of Espírito Santo — UFES, Brasil**. Este programa brinda atención dermatológica gratuita, especialmente a personas de bajos recursos que no pueden acceder fácilmente a tratamientos privados.

El dataset contiene imágenes clínicas de lesiones cutáneas tomadas con teléfonos inteligentes. Debido a que las imágenes fueron capturadas con diferentes dispositivos móviles, estas pueden presentar variaciones en tamaño, resolución, iluminación, enfoque y condiciones de adquisición.

Según la fuente original, el dataset contiene:

- **2.298 imágenes clínicas de lesiones cutáneas**
- **1.373 pacientes**
- **1.641 lesiones de piel**
- Imágenes en formato **PNG**
- Metadatos clínicos organizados en un archivo **CSV**
- Hasta **26 características clínicas** asociadas a cada muestra

Cada imagen está relacionada con información clínica del paciente y de la lesión, como edad, región anatómica, tipo de piel según Fitzpatrick, diámetro de la lesión y diagnóstico dermatológico.

## Clases diagnósticas del dataset

El dataset PAD-UFES-20 incluye lesiones cutáneas clasificadas en las siguientes categorías:

- **ACK**: Actinic Keratosis
- **BCC**: Basal Cell Carcinoma
- **MEL**: Melanoma
- **NEV**: Nevus
- **SCC**: Squamous Cell Carcinoma
- **SEK**: Seborrheic Keratosis

La fuente original también menciona **Bowen’s disease — BOD**. Sin embargo, esta lesión es considerada una forma de **SCC in situ**, por lo que en el dataset original fue agrupada dentro de la clase **SCC**. Por esta razón, el conjunto final se organiza en seis clases principales.

## Motivo de la separación del dataset

El dataset original se descarga con las imágenes y un archivo CSV de metadatos. En ese archivo CSV, cada imagen está identificada mediante la columna `img_id` y su diagnóstico se encuentra en la columna `diagnostic`.

Sin embargo, para entrenar modelos de clasificación de imágenes, especialmente redes neuronales convolucionales, resulta más práctico organizar las imágenes en carpetas separadas por clase. Esta estructura es común en frameworks de aprendizaje profundo como **PyTorch**, **TensorFlow** y **Keras**.

Por esta razón, en este proyecto se realizó una separación automática de las imágenes según su diagnóstico. El script de Python lee el archivo `x.csv`, toma el valor de la columna `diagnostic` y copia cada imagen a una carpeta correspondiente a su patología.

La estructura generada es la siguiente:

```text
dataset_clasificado_por_patologia/
├── ACK/
├── BCC/
├── MEL/
├── NEV/
├── SCC/
└── SEK/
````

Esta separación permite trabajar el dataset de manera más directa para tareas de inteligencia artificial, como:

* clasificación automática de lesiones cutáneas;
* entrenamiento de redes neuronales convolucionales;
* análisis de balance de clases;
* preparación de conjuntos de entrenamiento, validación y prueba;
* futuros despliegues en aplicaciones móviles o sistemas de apoyo diagnóstico.

Es importante aclarar que esta separación **no modifica el contenido original del dataset**, no cambia los diagnósticos y no altera las imágenes. Únicamente reorganiza los archivos en carpetas para facilitar su uso en modelos de visión por computador.

## Consideraciones éticas y de uso

De acuerdo con la descripción oficial del dataset, los datos fueron recolectados dentro del programa PAD de la UFES. El proyecto contó con aprobación del comité de ética de la universidad y con autorización mediante la Plataforma Brasil. Además, los datos fueron recolectados con consentimiento de los pacientes y preservando su privacidad.

El dataset se encuentra publicado bajo licencia **CC BY 4.0**, por lo que puede ser utilizado siempre que se cite correctamente la fuente original.

## Referencia

Pacheco, A. G. C., Lima, G. R., Salomão, A. S., Krohling, B., Biral, I. P., de Angelo, G. G., Alves Jr., F. C. R., Esgario, J. G. M., Simora, A. C., Castro, P. B. C., Rodrigues, F. B., Frasson, P. H. L., Krohling, R. A., Knidel, H., Santos, M. C. S., Espírito Santo, R. B., Macedo, T. L. S. G., Canuto, T. R. P., & de Barros, L. F. S. (2020). **PAD-UFES-20: a skin lesion dataset composed of patient data and clinical images collected from smartphones**. Mendeley Data, Version 1. [https://doi.org/10.17632/zr7vgbcyr2.1](https://doi.org/10.17632/zr7vgbcyr2.1)

```
```

[1]: https://data.mendeley.com/datasets/zr7vgbcyr2/1 "PAD-UFES-20: a skin lesion dataset composed of patient data and clinical images collected from smartphones - Mendeley Data"
