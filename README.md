# Detección de diabetes 

Este README proporciona una descripción del proyecto de detección de diabtes.

Nombre del dataset: [Diabetes Health Indicators Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset)

## Variables
Edad: Edad del paciente.
Masulino o femenino
Glucosa: Nivel de glucosa en sangre
IMC: Índice de masa corporal (IMC)
Presión arterial: Presión arterial del paciente 
Insulina: Nivel de insulina en sangre
Hipertensión: Valor binario que indica si el paciente sufre de hipertensión
Problemas cardiacos: Valor binario que indica si el paciente tiene problemas del corazón
Historial de fumador: Insica que tanto el paciente considera que fuma
Hemoglobina A1c: Cantidad de azúcar en la sangre

## Distribución de los datos

Inicialmente esta es la distribución de los datos:
* Train: 80,000 datos de entrenamiento
* Test: 20,000 datos de prueba


## Objetivo
El objetivo principal de este proyecto es desarrollar un modelo de predicción de diabetes utilizando técnicas de machine learning. Este modelo tiene aplicaciones en la detección temprana de la diabetes, lo que es fundamental para diversas aplicaciones como la atención médica preventiva y reducción de costos de diagnóstico
Desarrollar un modelo preciso de predicción de diabetes mediante machine learning representa una contribución significativa para la investigación en aprendizaje automático aplicado al sector salud

## Justificación y respaldo en la literatura
Este proyecto se basa en los resultados del paper "A practical framework for early detection of diabetes using ensemble machine learning models"

## Preprocesamiento de datos
* One-hot encoding: Se aplicó a variables categóricas (género e historial de fumador) para convertirlas en formato numérico compatible
* Imputación por moda: Se utilizó para completar los valores faltantes en el historial de fumador
* Normalización: Todos los datos fueron normalizados 
* División de datos: El dataset se dividió en conjuntos de entrenamiento y pruebas
  
## Arquitectura del modelo
El proyecto implementa un Perceptrón Multicapa (MLP) usando la API Sequential de Keras. Este modelo consta de 3 capas. Las primeras capas contienen 300 neuronas, ambas utilizando la función de activación ReLU. La capa de salida contiene 2 neuronas con activación Sigmoid, correspondientes a las categorías de clasificación para pacientes con diabetes.
El modelo se compila con el optimizador adam, un learning rate inicial de 0.001 y utiliza sparse_categorical_crossentropy como función de pérdida.

## Evaluación Inicial
* Accuracy: 0.971 - Indica que el modelo clasifica correctamente el 97.1% de los casos.
* Precision: 0.97 - Muestra que cuando el modelo predice un caso positivo, tiene una confiabilidad del 97%, con muy pocos falsos positivos.
* Recall: 0.83 - Revela que el modelo identifica correctamente el 83% de todos los casos reales de diabetes, aunque algunos casos positivos no son detectados.
* F1: 0.79- Este valor, que representa el equilibrio entre precisión y recall, sugiere un buen desempeño general del modelo, aunque hay espacio para mejorar en la identificación de casos positivos.

## Principales Cambios con Respecto al Modelo Base 
* Número de épocas: He aumentado el número de épocas a 20
* Funcion de activación: Cambio de softmax a sigmoid
* Numero de neuronas: En la primera y segunda capa se aumento el numero de neuronas a 300
* Nornalización: El StandardScaler se ajustó únicamente sobre el conjunto de entrenamiento y posteriormente se aplicó tanto al conjunto de pruebas

## Evaluación Final
* Accuracy: 0.9724 – Indica que el modelo clasifica correctamente el 97.24% de los casos.
* Precision: 0.9817 – Muestra que cuando el modelo predice un caso positivo, tiene una confiabilidad del 98.17%, con menos falsos positivos.
* Recall: 0.8378 – Revela que el modelo identifica correctamente el 83.78% de todos los casos reales de diabetes, mejorando levemente su capacidad de detección respecto a la versión anterior.
* F1: – Este valor, que representa el equilibrio entre precisión y recall, sugiere una mejora general en el rendimiento del modelo.

## Conclusiones
Aunque la mejora en las métricas del modelo puede parecer pequeña en términos porcentuales, en el contexto del sector salud, pueden tener un impacto significativo. Un aumento leve en el recall, por ejemplo, implica la detección de más casos reales de una condición como la diabetes, lo cual puede traducirse en diagnósticos más tempranos y mejores oportunidades de tratamiento. Por tanto, estas mejoras, aunque sutiles en apariencia, representan un progreso valioso en la efectividad del modelo en aplicaciones clínicas.

## Referencias
Saihood, Q., & Sonuç, E. (2023). A practical framework for early detection of diabetes using ensemble machine learning models. Turkish Journal of Electrical Engineering and Computer Sciences, 31(4), 722–738. https://doi.org/10.55730/1300-0632.4013
