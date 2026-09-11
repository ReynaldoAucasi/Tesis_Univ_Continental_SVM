# Tesis_Univ_Continental_SVM
# Modelo de clasificación para la asignación automática de tickets

Repositorio asociado a la investigación:

**“Modelo de clasificación para la asignación automática de tickets de un área de Soporte a Usuarios de una Entidad del Estado utilizando Machine Learning”**

## 1. Descripción

Este repositorio contiene el código fuente, la configuración, documentación y resultados asociados al desarrollo de un modelo de Machine Learning para la asignación automática de tickets a grupos resolutores del área de Soporte a Usuarios de una entidad del Estado.

El modelo utiliza técnicas de procesamiento de lenguaje natural para transformar la información textual de los tickets en representaciones numéricas y posteriormente realizar la asignación automática al grupo resolutor correspondiente.

## 2. Datos utilizados

La investigación utilizó registros históricos de tickets correspondientes a incidentes y requerimientos del área de Soporte a Usuarios.

El conjunto de datos empleado en la investigación contiene información correspondiente a **10 504 tickets**, asociados a **6 grupos resolutores y 16 servicios**.

Debido a las restricciones de confidencialidad y protección de datos de la entidad estudiada, los registros reales utilizados durante la investigación no se encuentran publicados en este repositorio.

Para facilitar la reproducibilidad metodológica, se proporciona:

- la estructura de los datos;
- la descripción de las variables;
- un conjunto de datos de ejemplo;
- el código de procesamiento y modelamiento;
- la configuración utilizada;
- el procedimiento de ejecución; y
- los principales resultados obtenidos.

## 3. Variables del modelo

Las variables consideradas en la investigación son:

| Variable | Tipo | Función |
|---|---|---|
| Tipo | Categórica | Variable de entrada |
| Servicio | Categórica | Variable de entrada |
| Categoría | Categórica | Variable de entrada |
| Descripción | Texto | Variable de entrada |
| Grupo Asignado | Categórica | Variable objetivo (target) |

La variable objetivo **Grupo Asignado** representa el grupo resolutor responsable de atender el ticket.

## 4. Metodología computacional

El procesamiento implementado comprende las siguientes etapas:

1. Preprocesamiento de los datos.
2. Limpieza y normalización del texto.
3. Tokenización.
4. Eliminación de palabras vacías (stopwords).
5. Stemming mediante el algoritmo Snowball.
6. Vectorización mediante TF-IDF.
7. Balanceo de las clases.
8. Entrenamiento y comparación de modelos de Machine Learning.
9. Evaluación mediante validación cruzada estratificada.
10. Selección y evaluación del modelo final SVM.

## 5. Modelos evaluados

Se compararon los siguientes algoritmos bajo condiciones homogéneas de evaluación:

- Support Vector Machine (SVM)
- Random Forest
- Regresión Logística
- Naive Bayes
- K-Nearest Neighbors (KNN)

La comparación se realizó utilizando la misma representación TF-IDF y el mismo esquema de validación cruzada.

## 6. Configuración principal

La configuración documentada para el experimento incluye:

| Parámetro | Valor |
|---|---|
| División entrenamiento/prueba | 80 % / 20 % |
| Validación cruzada | Stratified K-Fold |
| `Número de folds` | 5 |
| `Vectorizador` | TF-IDF |
| `ngram_range` | `(1,1)` |
| `min_df` | `2` |
| `max_df` | `0.95` |
| `norm` | `l2` |
| `max_features` | `1000` |
| Algoritmo final | SVM |
| Kernel | Lineal |
| `random_state` | `42` |

## 7. Entorno de ejecución

El desarrollo y evaluación del modelo se realizaron utilizando:

- Python 3.12.7
- Anaconda
- Visual Studio Code 1.96.2

## 8. Resultados

El modelo SVM seleccionado alcanzó los siguientes resultados en el conjunto de prueba:

| Métrica | Resultado |
|---|---:|
| Accuracy | 0.72 |
| Precision macro | 0.76 |
| Recall macro | 0.74 |
| F1-score macro | 0.75 |
| F1-score weighted | 0.72 |

El conjunto de prueba estuvo conformado por **2 101 tickets**.

Los resultados detallados de la comparación de modelos y de la evaluación del modelo SVM se encuentran en la carpeta `resultados/`.

## 9. Reproducibilidad

Este repositorio proporciona los elementos necesarios para reproducir el flujo metodológico de procesamiento, entrenamiento y evaluación del modelo.


## 10. Referencia de la investigación

Aucasi, R., & Costilla, N. (2026). *Modelo de clasificación para la asignación automática de tickets de un área de Soporte a Usuarios de una Entidad del Estado utilizando Machine Learning* [Tesis de maestría, Universidad Continental].
