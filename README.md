# Clasificaci-n-b-sica-Predicci-n-de-Calidad-del-Vino-Core-
Predicción de Calidad del Vino
Predicción de Calidad del Vino Tinto
Descripción del Proyecto
Este proyecto tiene como objetivo construir y evaluar modelos de clasificación para predecir la calidad del vino tinto basándose en sus características físico-químicas. Se exploran y comparan diferentes algoritmos de machine learning para determinar cuál ofrece el mejor rendimiento en esta tarea de clasificación multiclase.

Dataset
El dataset utilizado es el "Wine Quality Dataset" disponible en Kaggle (referencia: yasserh/wine-quality-dataset). Contiene datos sobre varias propiedades de vinos tintos y una puntuación de calidad asociada (en una escala del 0 al 10).

Las características incluidas son:

Acidez fija
Acidez volátil
Ácido cítrico
Azúcar residual
Cloruros
Dióxido de azufre libre
Dióxido de azufre total
Densidad
pH
Sulfatos
Alcohol
Calidad (variable objetivo)
Id (identificador, excluido del modelado)
Análisis y Preprocesamiento de Datos
Se realizó un análisis exploratorio inicial para entender la estructura del dataset, describir las variables y verificar la presencia de valores nulos o atípicos. El dataset no presentó valores faltantes. Se observó un desbalance significativo en las clases de calidad del vino, con la mayoría de las muestras concentradas en las calidades 5 y 6.

El preprocesamiento incluyó:

Separación de la variable objetivo ('quality') y las características.
División del dataset en conjuntos de entrenamiento y prueba (80% entrenamiento, 20% prueba).
Escalado de las características numéricas utilizando StandardScaler para que los modelos no se vean afectados por las diferentes escalas de las variables.
Modelos de Clasificación
Se entrenaron y evaluaron tres modelos de clasificación:

K-Nearest Neighbors (KNN)
Random Forest
Regresión Logística
Para cada modelo, se realizó una optimización de hiperparámetros utilizando GridSearchCV con validación cruzada (5 folds) para encontrar la mejor configuración.

Evaluación de Modelos
Los modelos fueron evaluados en el conjunto de prueba utilizando métricas como:

Precisión (Accuracy)
Informe de Clasificación (Precision, Recall, F1-Score por clase)
Matriz de Confusión
Curvas ROC y Área Bajo la Curva (AUC) por clase (para el mejor modelo)
Resultados Clave
Random Forest fue el modelo con el mejor rendimiento general basado en la métrica de precisión (Accuracy) en el conjunto de prueba.
Todos los modelos mostraron dificultades significativas para clasificar correctamente las clases minoritarias de calidad del vino (especialmente las calidades 3, 4, 7 y 8) debido al desbalance de clases inherente en el dataset.
La Regresión Logística tuvo el rendimiento más bajo, probablemente debido a su naturaleza lineal.
El análisis de las curvas ROC para Random Forest confirmó que el modelo es más efectivo distinguiendo entre las clases mayoritarias (5 y 6).
Conclusiones
El modelo Random Forest demostró ser el más prometedor para predecir la calidad del vino en este dataset, aunque el desbalance de clases representa un desafío importante, afectando la capacidad del modelo para predecir con precisión las calidades menos frecuentes.

Para mejorar el rendimiento, especialmente en las clases minoritarias, se podrían explorar técnicas de manejo de desbalance de clases (como sobremuestreo o submuestreo) o investigar algoritmos de clasificación más avanzados.

Cómo Ejecutar el Código
Clona este repositorio de GitHub.
Asegúrate de tener Python y las librerías necesarias instaladas (pandas, sklearn, matplotlib, kagglehub). Puedes instalarlas usando pip:


