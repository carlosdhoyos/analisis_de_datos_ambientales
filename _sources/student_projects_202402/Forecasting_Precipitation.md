# Review de Técnicas de Forecasting de Precipitación


## Introducción
La predicción de la precipitación es crucial en sectores como la agricultura, la gestión de recursos hídricos y la producción de energía hidroeléctrica, ya que su variabilidad tiene un impacto directo en la economía y el bienestar de las poblaciones. La complejidad de los sistemas involucrados, que incluyen factores topográficos, hidrológicos y atmosféricos, hace que el pronóstico sea un reto a considerar. A pesar de los avances en la implementación de modelos numéricos y estadísticas para la predicción de precipitaciones, los eventos de lluvia extrema siguen siendo particularmente difíciles de prever, lo que puede generar desastres naturales como inundaciones, deslizamientos de tierra y sequías.

Recientemente, los avances en el modelado de la precipitación han incorporado enfoques modulares que combinan diferentes submodelos para capturar los diversos procesos físicos de la lluvia. Estos enfoques permiten abordar la complejidad inherente a la predicción de precipitaciones, mejorando la capacidad de los modelos para hacer frente a la variabilidad espacio-temporal y la incertidumbre asociada con los pronósticos. Además, el uso de modelos probabilísticos está ganando terreno frente a los modelos deterministas tradicionales, ya que ofrecen una representación más adecuada de la incertidumbre y ayudan a los responsables de la toma de decisiones a gestionar los recursos de manera más efectiva.

La importancia de la predicción de la precipitación se ve reflejada no solo en la gestión de los recursos hídricos, sino también en su impacto directo sobre las actividades agrícolas, donde la planificación oportuna de las siembras y cosechas puede evitar pérdidas significativas. Los modelos numéricos operativos y los datos provenientes de radares meteorológicos son herramientas fundamentales en este proceso, pero la necesidad de mejorar su precisión y fiabilidad sigue siendo un reto. Así, el desarrollo de nuevos enfoques que integren técnicas de aprendizaje automático y modelos híbridos podría marcar la diferencia en la evolución de la predicción de precipitaciones, permitiendo obtener así predicciones cada vez más precisas, siendo esto una mejor herramienta a la hora de tomar decisiones.

---

## Review of Key Papers

### Paper 1: A Rainfall Forecasting Method Using Machine Learning Models and its Application to the Fukuoka City Case.
- **Autores:** S. Monira Sumi, M. Faisal Zaman, Hideo Hirose.
- **Aspectos Clave:** 
  - El uso de varios modelos de Machine Learning para la construcción de un método híbrido de pronóstico y comparación con ellos.
  - Preprocesamiento para optimizar entradas en los modelos.

- **Datos:**
  - El estudio usó una serie de precipitación diaria de la temporada de lluvias y una serie de precipitaciones mensuales.
  - Los datos fueron obtenidos de estaciones meteorológicas cercanas, dentro de un rango de 48 km de la ciudad de Fukuoka.

- **Metodología:**
  - **Preprocesamiento de los datos:** Media móvil, análisis de componentes principales.  
  - **Construcción de inputs/outputs pairs:** Reorganización de las series de tiempo como vectores de retraso.
  - **Métodos individuales de Machine Learning:** Se seleccionaron 4 modelos de Machine Learning para construir el método híbrido de pronóstico multimodelo. Se seleccionaron ANN, KNN, MARS y SVR.
  - **Método híbrido de pronóstico multimodelo:** Se construyen submodelos y se eligen los más precisos para con ellos crear el método híbrido de pronóstico.
  - **Pruebas estadísticas:** Se empleó la prueba de Diebold-Mariano para comparar la diferencia entre los pronósticos de dos métodos competidores.
  - Se analizaron métricas de error a partir de la predicción del próximo paso de tiempo.

- **Resultados Clave:**
  - Se encontró que el análisis de componentes principales en el preprocesamiento, produce más eficiencia, por lo cual se usan las series reconstruidas de este para entrenar los modelos.
  - En el caso de las series diarias de precipitaciones, el modelo híbrido de múltiples modelos produjo el pronóstico más preciso de todos los modelos individuales y en el de las series mensuales, también fue de los mejores.


- **Herramientas de Machine Learning:**
  - **Artificial Neural Network (ANN):** Consiste en un número de capas ocultas y un número de neuronas en la capa de entrada, las capas ocultas y la capa de salida.
  - **K-Nearest Neighbor (KNN):** Es un método no paramétrico que basa su predicción en las salidas objetivo de los k-vecinos más cercanos al punto de consulta dado.
  - **Multivariate Adaptive Regression Splines (MARS):** Fue propuesto como una técnica de modelado local basada en árboles, que divide el espacio de datos en varias regiones, posiblemente superpuestas, y ajusta funciones spline truncadas en cada región.
  - **Support Vector Regression (SVR):** Es un método que penaliza la complejidad resultante mediante un término de penalización añadido a la función de error.
  
- **Fortalezas:** 
  - Aproximación al problema desde distintas herramientas de Machine Learning.
  - Optimización de datos de entrada para los modelos de Machine Learning.

- **Limitaciones:** 
  - Sensibilidad a la selección de parámetros.
  - La metodología híbrida puede llevar a un alto coste computacional.

- **Relevancia para el Forecasting:**
    Ofrece un buen marco teórico de los modelos seleccionados, además de mostrar que el método híbrido que construyeron es la mejor forma de predecir la precipitación diaria entre las evaluadas, incluso tambien a escala mensual.
    
### Paper 2: Rainfall Forecasting Model Using Machine Learning Methods: Case Study Terengganu, Malaysia.

- **Autores:** Wanie M. Ridwan et.al.
- **Aspectos Clave:** 
  - Se hace una comparativa entre 4 modelos de Machine learning para predecir la precipitación en el área del lago Kenyir en Terengganu, Malasia.
  - Incorpora técnicas de validación cruzada y ajuste de hiperparámetros que pueden ayudar a mejorar la precisión de la predicción en distintas ventanas de tiempo.

- **Datos:**
  - Los datos para este estudio consisten en 10 estaciones que cubren el área del Lago Kenyir en Hulu Terengganu.
  - Se usa el método de polígono de Thiessen para calcular el peso de la lluvia de cada estación y el promedio de lluvia basado en cada estación. 

- **Metodología:**
  - Se seleccionan 4 modelos de Machine Learning (BLR, BDTR, DFR, NNR)
  - Se busca predecir la lluvia en diferentes horizontes temporales utilizando diferentes algoritmos de Machine Learning
  - Para el análisis de los escenarios temporales, se usan dos métodos, función de autocorrelación y error proyectado.
  - Se tienen en cuenta los siguientes indicadores (MAE, RMSE, RAE, RSE, R)

- **Resultados Clave:**
  - Para el primer método, se encontró que la mejor regresión desarrollada es BDTR, ya que tiene el coeficiente de determinación más alto.
  - Sin ajuste, el modelo BDTR no tuvo un buen desempeño; sin embargo, se notó una mejora significativa en la precisión del modelo propuesto tras incorporar técnicas de validación cruzada y ajuste de hiperparámetros. 
  - Para el segundo método, BDTR y DFR, presentaron la mayor precisión en la mayoría de ventanas temporales.
  
- **Herramientas de Machine Learning:**
  - **Bayesian Linear Regression (BLR):** La principal ventaja de este procesamiento bayesiano es que recupera toda la gama de soluciones inferenciales, en lugar de limitarse a una estimación puntual y un intervalo de confianza como ocurre en la regresión clásica.
  - **Boosted Decision Tree Regression (BDTR):** Es un método clásico para crear un conjunto de árboles de regresión donde cada árbol depende del árbol anterior.
  - **Decision Forest Regression (DFR):** Es un conjunto de árboles de decisión entrenados de manera aleatoria. Funciona construyendo un gran número de árboles de decisión durante la etapa de entrenamiento.
  - **Neural Network Regression (NNR):** Es una cadena de operaciones lineales intercaladas con diversas funciones de activación no lineales.
  
- **Fortalezas:** 
  - Diversidad de métodos y escenarios
  - Optimización de modelos a partir de técnicas de validación cruzada y ajuste de hiperparámetros.

- **Limitaciones:** 
  - Los resultados del segundo método dependen mucho de la normalización usada para los datos
  - Aunque el BDTR fue el modelo que presentó mejor rendimiento, este requiere mayor costo computacional.


- **Relevancia para el Forecasting:**
    Muestra la importancia del ajuste de optimizar el modelo a partir de técnicas de validación cruzada y ajuste de hiperparámetros, además de mostrar una superioridad a la hora de predecir precipitación del método de función de autocorrelación sobre el de error proyectado, basado en que este fue capaz de representar los patrones de lluvia.

### Paper 3: Rainfall Prediction Using Machine Learning Techniques for Sabarmati River Basin, Gujarat, India.
- **Autores:** Anant Patel et.al.
- **Aspectos Clave:** 
  - Comparación entre diversos modelos de Machine Learning.
  - Se hace uso de un análisis exploratorio de los datos para comprender su variabilidad antes de entrar en los modelos.
  
- **Datos:**
  - Datos diarios de precipitación recopilados del acceso regional de datos POWER del sitio web de la NASA. 

- **Metodología:**
  - Se realizó un análisis exploratorio a los datos para resumir sus principales características.
  - Se seleccionan tres modelos de Machine Learning (RFR, GBA, DTC)
  - Se usó el 70% de los datos para training en los 3 modelos.
  - Selección de algunas métricas de rendimiento para ver el comportamiento de los modelos.
  
- **Resultados Clave:**
  - El GBA fue el modelo demostró el mejor rendimiento entre los 3 modelos, con una precisión del 93%
  - Identificación de variables clave, como la humedad, que afectan significativamente la precisión de las predicciones.
  
- **Herramientas de Machine Learning:**
  - **Random Forest Regressor (RFR):** Es un algoritmo de aprendizaje supervisado basado en ensamblaje. Este enfoque combina múltiples aprendices débiles (en este caso, árboles de decisión) para formar un único predictor fuerte.
  - **Gradient Boosting Algorithm (GBA):** Aquí muchos modelos se entrenan de manera secuencial, de forma gradual y aditiva, para convertir los aprendices débiles en fuertes. A medida que se repiten los pasos, cada árbol intenta minimizar el error residual.
  - **Decision Tree Classifier (DTC):** Es una técnica de aprendizaje supervisado que puede utilizarse tanto para problemas de clasificación como de regresión, aunque generalmente se prefiere para el primero.
  
- **Fortalezas:** 
  - Uso de un conjunto de datos amplio y detallado
  - Análisis de varios modelos de Machine Learning, permitiendo la comparación de los resultados
  
- **Limitaciones:** 
  - Los resultados no son aplicables a otros lugares.
  - Aunque se menciona la importancia de eventos extremos, no son tenidos en cuenta
  
- **Relevancia para el Forecasting:**
    Se hace énfasis y se muestra como un análisis exploratorio de los datos, antes de entrar a los modelos, puede ayudar a identificar patrones y variables clave que pueden ayudar a mejorar la precisión de las predicciones.

### Paper 4: Development of Advanced Artificial Intelligence Models for Daily Rainfall Prediction.

- **Autores:** Binh Thai Pham et.al
- **Aspectos Clave:** 
  - Presenta una alternativa a la predicción tradicional con modelos climáticos en conjunción con radares, usando Machine Learning.
  - Se presenta y compara un modelo de Machine Learning híbrido, usando optimización.
  
- **Datos:**
  - Datos de precipitación recopilados a través de un pluviómetro ubicado en el distrito de Cao Phong, provincia de Hoa Binh, Vietnam.
  - Los datos meteorológicos se obtuvieron del Global Weather Data for SWAT.
  - Datos de GFS fueron usados, se aplicaron técnicas de downscaling para adaptarlos a la zona de estudio.
  
- **Metodología:**
  - Se seleccionan varios modelos de Machine Learning (PSO-ANFIS, ANN, SVM)
  - Uso de varios criterios de validación para analizar la precisión de los modelos desarrollados (R, MAE, SS, POD, CSI, FAR)
  - Se utiliza el método de Monte Carlo (1000 simulaciones) con el fin de investigar la robustez de los tres modelos de IA.
  - El 70% de los datos fue usado para training.
  
- **Resultados Clave:**
  - Analizando los valores de Skill Score (SS), los modelos de IA propuestos mostraron una mejora en la predicción con respecto a los datos de GFS.
  - A través de las simulaciones de Monte Carlo se encontró que el modelo SVM, demostró tener mayor robustez que los otros dos.
  - Los tres modelos de IA propuestos, especialmente el SVM, muestran una gran capacidad para rastrear el comportamiento del proceso de lluvia al pasar de un período sin lluvia a un período con lluvia.
  
- **Herramientas de Machine Learning:**
  - **Artificial Neural Networks (ANN):** Son un modelo computacional basado en la estructura y funciones de las redes neuronales biológicas.
  - **Adaptive network based fuzzy inference system (ANFIS):** Es una combinación entre las reglas de aprendizaje de redes adaptativas y un sistema de inferencia difusa. 
  - **Particle Swarm Optimization (PSO):** Es una técnica de inteligencia de enjambre eficiente propuesta y desarrollada en base al comportamiento social de los bandos de aves para resolver problemas complejos de optimización.
  - **Support Vector Machines (SVM):** Es un algoritmo de aprendizaje supervisado que analiza datos para clasificación y regresión.
  
- **Fortalezas:** 
  - Se muestra como el uso del modelo híbrido PSO-ANFIS ofreció resultados competitivos, dejando así a la vista ventajas potenciales en configuraciones que necesitan optimización adicional.
  
- **Limitaciones:** 
  - Falta de capacidad computacional para un análisis más robusto del Skill Score usando los datos de GFS.
  - Las variables usadas para entrenar los modelos no son las más apropiadas para presentar el proceso físico de precipitación en un período de 24 horas.
  
- **Relevancia para el Forecasting:**
    Se muestra un enfoque diferente a los métodos tradicionales de predicción, obteniendo así mayor precisión al momento de usar IA, además de presentar el potencial de los modelos híbridos, como un campo para explorar y desarrollar.
    
### Paper 5:  Rainfall Prediction for the Kerala State of India Using Artificial Intelligence Approaches.
- **Autores:** Yajnaseni Dash, Saroj K. Mishra, Bijaya K. Panigrahi.
- **Aspectos Clave:** 
  - Se señala la importancia de una buena selección de los nodos ocultos, buscando mejorar la precisión evitando el sobreajuste.
  - Comparativa entre distintos modelos de Machine Learning.
  
- **Datos:**
  - Los datos de series temporales fueron recolectados del Instituto Indio de Meteorología Tropical (IITM) en Pune para la subdivisión de Kerala.
  - Se utilizaron las series temporales mensuales medias de monzón de verano (JJAS) y post-monzón (OND) para fines de predicción.
  
- **Metodología:**
  - Se hace normalización a los datos antes de ingresarlos a los modelos.
  - Se usaron los datos de 1871-2010 para training y los datos de 2011-2016 para test.
  - Se seleccionaron los modelos de Machine Learning (KNN, ANN, ELM).
  - Se consideraron diferentes parámetros estadísticos para calcular el rendimiento de los modelos de inteligencia artificial propuestos (MAE, PP, RSME, MASE).
  
- **Resultados Clave:**
  - Los modelos ANN y ELM mostraron mayor precisión a la hora de predecir la lluvia, debido a la presencia de nodos ocultos.
  - El costo computacional de KNN fue el más bajo, pero obtuvo los mayores errores de predicción.
  
- **Herramientas de Machine Learning:**
  - **K-nearest neighbor (KNN):** Es una técnica sofisticada en la que se debe encontrar un grupo de k objetos en el conjunto de datos de entrenamiento que estén cerca del objeto de datos de prueba.
  - **Artificial Neural Networks (ANN):** Comprende neuronas conectadas entre la capa de entrada, la capa oculta y las capas de salida. 
  - **Extreme learning machine (ELM):** ESe ha utilizado para superar el tiempo computacional extenso que requiere el aprendizaje por retropropagación del enfoque de redes neuronales de avance directo.
  
- **Fortalezas:** 
  - Comparación del coste computacional entre los modelos, para tener un mejor panorama a la hora de seleccionar.
  
- **Limitaciones:** 
  - No se tuvieron en cuenta otras variables para predecir la precipitación.
  
- **Relevancia para el Forecasting:**
    En este artículo se muestra como una adecuada selección de los nodos ocultos en modelos como ANN y ELM, pueden mejorar significativamente la precisión de la predicción.
    
---

## Comparison of Approaches
| Método                  | Fortalezas                               | Limitaciones                                                                 | Papers ejemplo                  |
|--------------------------|-----------------------------------------|-----------------------------------------------------------------------------|---------------------------------|
| K-Nearest Neighbor               | Modelo no paramétrico, Simplicidad         | Costo computacional alto con datasets grandes, Determinación de k      | Sumi et.al., Dash et.al.                  |
| Boosted Decision Tree Regression      | Robustez frente a datos faltantes                 | Propenso al sobre ajuste   | Ridwan et.al.                 |
| Gradient Boosting              | Análisis robusto de características      | Costo computacional alto con datasets grandes   | Patel et.al. |
| Artificial Neural Networks              | Versatilidad, Manejo eficiente de datos grandes       | Requieren un gran volumen de datos, Sensibilidad a la configuración de hiperparámetros  | Sumi et.al, Pham et.al., Dash et.al.                        |
| Extreme learning machine  | Entrenamiento rápido, Manejo eficiente de datos grandes   | Dificultad a la hora de seleccionar el número de neuronas en la capa oculta   | Dash et.al.                  |

---

## Challenges and Future Directions
- La predicción de eventos extremos aún es un campo que tiene mucho camino de investigación.
- Mejorar la integración de los procesos físicos en los modelos de Machine Learning.
- Optimización de los modelos para reducir el costo computacional.
- Hay todo un campo de exploración en cuanto a la selección óptima de parámetros en los modelos.
- Implimentación de modelos híbridos que combinen las mejores características de varios modelos.
- Mejora en la calidad y disponibilidad de datos.
- Desarrollo de modelos generalizables a otros lugares.

---

## Conclusión
La predicción de la precipitación ha evolucionado significativamente, integrando enfoques avanzados que combinan técnicas tradicionales y emergentes. A través de la revisión de múltiples estudios, se identificaron tendencias clave que apuntan al creciente protagonismo del Machine Learning y los modelos híbridos como herramientas fundamentales para mejorar la precisión en los pronósticos, a partir de modelos como Artificial Neural Networks, Gradient Boosting, Boosted Decision Tree Regression, entre otros. 

Los avances incluyen el uso de validación cruzada y ajuste de hiperparámetros para optimizar los modelos, el desarrollo de técnicas híbridas que combinan múltiples metodologías, y el enfoque en datos específicos y de alta resolución espacial. A pesar de estas mejoras, persisten desafíos como la alta complejidad computacional, la sensibilidad a la parametrización y la generalización limitada a diferentes regiones geográficas.

Es por todo esto que la implementación de enfoques híbridos y modulares que integren el Machine Learning con técnicas probabilísticas ofrece un camino prometedor para abordar la variabilidad espacio-temporal de las precipitaciones y su impacto en sectores clave como la agricultura y la gestión de recursos hídricos. El desarrollo continuo en este campo permitirá generar modelos más robustos, precisos y útiles para la toma de decisiones en contextos de alta incertidumbre.


---

## Questions About Methodologies and ML Approaches

- ¿Qué técnicas de preprocesamiento se implementaron?
- ¿Cómo seleccionaron el porcentaje de datos para el training?
- ¿Cómo elegieron la métrica de error adecuada a minimizar?
- ¿Cuál es la arquitectura de los modelos aplicados?
- ¿Cómo se podría reproducir el experimento en otras zonas de estudio?
- ¿Cualés son los requerimientos computacionales necesarios para correr los modelos?
- ¿En que áreas es posible optimizar los modelos?


---

## Referencias
1. Dash, Y., Mishra, S. K., & Panigrahi, B. K. (2018). Rainfall prediction for the Kerala state of India using artificial intelligence approaches. Computers & Electrical Engineering, 70, 66-73.
2. Patel, A., Keriwala, N., Soni, N., Goel, U., Bhoj, R., Adhyaru, Y., & Yadav, S. M. (2023). Rainfall Prediction using Machine Learning Techniques for Sabarmati River Basin, Gujarat, India. Journal of Engineering Science & Technology Review, 16(1).
3. Pham, B. T., Le, L. M., Le, T. T., Bui, K. T. T., Le, V. M., Ly, H. B., & Prakash, I. (2020). Development of advanced artificial intelligence models for daily rainfall prediction. Atmospheric Research, 237, 104845.
4. Ridwan, W. M., Sapitang, M., Aziz, A., Kushiar, K. F., Ahmed, A. N., & El-Shafie, A.(2021). Rainfall forecasting model using machine learning methods: Case study Terengganu, Malaysia. Ain Shams Engineering Journal, 12(2), 1651-1663.
5. Sumi, S. M., Zaman, M. F., & Hirose, H. (2012). A rainfall forecasting method using machine learning models and its application to the Fukuoka city case. International Journal of Applied Mathematics and Computer Science, 22(4), 841-854.

