# ExAnDB
## 190304018-1 ANÁLISIS DE DATOS 2026-1

### Segunda evaluación

### Integrantes:
#### JESSICA JOHANNA OBANDO GARC�A
#### MATEO GONZALEZ ESCUDERO
#### LUKAS JIMENEZ BUENO

## Fase 1 -- Exploración bases de datos

## Selección bases de datos

### Base de Datos 1: Tabular (numérica y categórica)
#### Nombre: Adult Income Dataset (Kaggle)
#### Fuente y tipo de datos: Secundaria (recopilación de encuestas de ingresos de adultos en EE. UU.)
#### Características básicas:
#### Número de registros: 48,842
#### Atributos: 14 (edad, educación, ocupación, ingresos, etc.)
#### Tamaño aproximado: 4 MB
#### Nivel de documentación: Alta; incluye descripción de atributos, valores posibles y contexto de la recolección.
#### Posibles aplicaciones: Predicción de ingresos, análisis socioeconómico, clasificación supervisada.
### Base de Datos 2: Texto
#### Nombre: IMDb Movie Reviews (Kaggle)
#### Fuente y tipo de datos: Secundaria (compilación de reseñas de películas de IMDb)
#### Características básicas:
#### Número de registros: 25,000 reseñas
#### Atributos: 2 (texto de la reseña, etiqueta de sentimiento: positivo/negativo)
#### Tamaño aproximado: 40 MB
#### Nivel de documentación: Media; incluye información sobre etiquetas de sentimiento y estructura del dataset.
#### Posibles aplicaciones: Análisis de sentimiento, minería de opiniones, modelos de procesamiento de lenguaje natural.
### Base de Datos 3: Imágenes
#### Nombre: CIFAR-10
#### Fuente y tipo de datos: Primaria (Kaggle)
#### Características básicas:
#### Número de registros: 10,000 imágenes 
#### Atributos: 32×32 píxeles, 3 canales RGB, 10 clases
#### Tamaño aproximado: 162 MB
#### Nivel de documentación: Alta; documentación oficial con descripción de clases, estructura de archivos y ejemplos.
#### Posibles aplicaciones: Clasificación de imágenes, entrenamiento de redes neuronales, proyectos de visión artificial.

## Justificacion de la selección de bases de datos

##### Tras la exploración de tres bases de datos distintas —una tabular (Adult Income Dataset), una de texto (IMDb Movie Reviews) y una de imágenes (CIFAR-10)— se ha decidido seleccionar la base de datos tabular por las siguientes razones:

### Manejabilidad y facilidad de análisis
##### La base de datos tabular permite un análisis directo con herramientas estándar de Python como pandas y seaborn, lo que facilita la limpieza, transformación y visualización de los datos. A diferencia de las bases de datos de imágenes o texto, que requieren preprocesamiento avanzado (vectorización de texto, transformación de imágenes, etc.), la estructura tabular permite concentrarse en la exploración estadística y análisis multivariado de manera eficiente.
### Documentación completa y clara
##### El Adult Income Dataset cuenta con documentación detallada de cada atributo, incluyendo rangos, valores posibles y descripción del contexto de recolección. Esto asegura que podamos interpretar correctamente los datos y comprender los resultados del análisis sin ambigüedades, lo que es crucial para la fase de EDA y la construcción de hipótesis.
### Relevancia y aplicabilidad
##### La base de datos contiene variables socioeconómicas y demográficas reales que permiten realizar análisis significativos sobre ingresos y factores asociados, como educación, edad, ocupación o horas trabajadas. Esto proporciona un contexto claro para explorar patrones, detectar relaciones y formular hipótesis verificables.
### Completitud y calidad de los datos
##### Aunque algunas variables presentan valores faltantes, estos son limitados y se pueden tratar fácilmente mediante imputación o categorización (“desconocido”). Esto permite conservar la mayoría de los registros y mantener la integridad del análisis sin comprometer los resultados.
### Versatilidad para diferentes tipos de análisis
##### La estructura tabular de esta base permite realizar análisis univariado, multivariado, correlaciones, tablas cruzadas y visualizaciones estadísticas de manera directa, cumpliendo con todos los requerimientos de la fase 2 (EDA).



# Insights principales del EDA

A partir del análisis exploratorio de datos realizado sobre el dataset *Adult Income*, se identificaron los siguientes hallazgos relevantes:

---

## 1. Presencia significativa de datos faltantes en variables clave
Se identificó que variables como `workclass`, `occupation` y `native-country` presentaban una cantidad considerable de valores faltantes. Este problema fue abordado mediante la imputación de la categoría `"Unknown"`, permitiendo conservar los registros sin perder información relevante.

---

## 2. Existencia de numerosos valores atípicos en variables numéricas
Variables como `capital-gain`, `capital-loss` y `hours-per-week` presentan una alta cantidad de valores atípicos (outliers), lo que indica la presencia de comportamientos extremos dentro de la población analizada.

---

## 3. Distribuciones altamente sesgadas en variables económicas
Las variables `capital-gain` y `capital-loss` presentan una fuerte asimetría positiva, con una gran concentración de valores en cero y algunos valores extremadamente altos. Esto sugiere la necesidad de aplicar transformaciones (como logaritmos) para mejorar su análisis.

---

## 4. Predominio de ciertas categorías en variables categóricas
Se observa una alta concentración en categorías específicas como `Private` en `workclass`, `HS-grad` en educación, `Male` en género y `United-States` en país de origen, evidenciando un desbalance en la distribución de estas variables.

---

## 5. Relación clara entre nivel educativo e ingresos
El análisis de tablas cruzadas evidencia que a mayor nivel educativo, mayor es la proporción de individuos con ingresos superiores a 50K, lo que sugiere una relación directa entre educación y nivel de ingresos.

---

## 6. Relación entre variables laborales y nivel de ingreso
Los análisis multivariados muestran que variables como `hours-per-week` y `capital-gain` presentan diferencias relevantes según el nivel de ingreso, indicando que estas variables pueden influir en la clasificación del ingreso.

---

## 7. Correlaciones débiles entre variables numéricas
El análisis de correlación indica que no existen relaciones lineales fuertes entre la mayoría de variables numéricas, lo que sugiere que el ingreso depende de múltiples factores y no de una sola variable dominante.

---