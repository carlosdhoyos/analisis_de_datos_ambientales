**Nombre: Natalia Andrea Pino Serna**
# Introducción 
La humedad del suelo juega un papel fundamental en la mejora de los modelos predictivos de movimientos en masa, los cuales tradicionalmente se han enfocado en umbrales de precipitación. Sin embargo, estos enfoques no consideran el comportamiento del agua en el suelo que es un factor importante para entender con mayo precisión la ocurrencia de movimientos en masa. En la actualidad, los sensores in situ de humedad están ganando relevancia en el estudio de estos fenómenos, ya que permiten obtener datos más detallados y específicos sobre las condiciones del suelo, incluso, dentro del Sistema de Alertas Tempranas del Valle de Aburrá (SIATA), existe una red de sensores instalados para monitorear la humedad del suelo. Sin embargo, estos sensores cuentan con retos como fallos técnicos que generan huecos en las lecturas o picos que se entienden poco en los datos. Por esta razón, predecir cómo se comportará la humedad del suelo de de gran relevancia, ya que no solo ayudaría a corregir los errores de datos causados por fallos en los sensores, sino que también mejoraría la aplicación de estos datos en la predicción de movimientos en masa, lo que proporciona un enfoque más preciso  de estos datos en la gestión del riesgo de desastres.

La predicción de la humedad del suelo mediante machine learning es de gran importancia debido a su impacto en la agricultura, la gestión de recursos hídricos y su aplicabilidad a sistemas de alerta temprana para desastres de origen natural (Huffake et al., 2024; Wang et al., 2024). Las redes de sensores inalámbricos permiten la recolección de grandes volúmenes de datos sobre la humedad del suelo, que presentan patrones influenciados por la precipitación y las propiedades del suelo, pero también pueden tener irregularidades debido a fallos en los sensores y procesos no lineales (Vereecken, 2016;  Huffake et al., 2024; Togneri et al., 2022). Los modelos tradicionales de balance hídrico, aunque son útiles, tienen limitaciones para predecir estos fenómenos de manera precisa y con alta resolución temporal (Jensen & Allen, 2016). En este sentido, el uso de machine learning, como los modelos LSTM, permite capturar dinámicas no lineales y complejas, mejorando la precisión de las predicciones (Wang et al., 2024; Custódio et al., 2024 ). Teniendo como resultado que el estudio de la humedad del suelo mediante técnicas de ML es esencialpara mejorar la gestión de recursos hídricos, optimizar actividades de agricultura y ser de gran utilidad en la Gestión del Riesgo de Desastres, asociado a fenómenos amenazante como inundaciones y movimientos en masa (Vereecken et al., 2022; Sampathkumar et al., 2013; Basak et al., 2023).



# **Paper 1**
## Título: 
Sensor records can be used to forecast complex soil moisture dynamics with symbiosis of empirical nonlinear dynamics and echo state neural network AI
## Autores: 
Ray Huffaker, Rafael Muñoz-Carpena, Kati W. Migliaccio.
## Ideas principales:
- El articulo busca reconstruir la dinámica de la humedad del suelo a partir de registros de sensores, mediante modelos de redes neuronales de ecoestado (ESNN), empleando arquitecturas ESNN hábiles como gemelos digitales para pronosticar niveles de humedad del suelo del mundo real fuera de muestra.
- La aplicación operativa de la ESNN a datos como la humedad tiene repercusiones más amplias a la hora de abordar problemas medioambientales acuciantes relacionados con procesos biofísicos no lineales y de crear sistemas de alerta temprana basados en IA que pronostiquen fenómenos medioambientales extremos (inundaciones, sequías, deslizamientos, incendios).
- Las ESNN pueden aprender dinámicas no lineales complejas a partir de datos limpios generados por modelos «de juguete» cerrados con dinámicas de espacio de estados conocidas.
- Para la humedad se infieren las dinámicas de espacio de estados.
- Un modelo RNN que sufre este problema no consigue aprender dependencias a largo plazo en datos secuenciales, ya que los pesos del modelo sólo se actualizan para los efectos cercanos.
- SSA es útil para aislar ruido en señales no periódicas
## Datos: 
dos registros de contenido volumétrico de agua en el suelo de sensores que representaban diferentes prácticas de riego recogidas en ensayos de campo en el sur de Florida. Estos datos son de un año con una resolución temporal de 1 h.

## Metodología: 
1. Preprocesamiento de datos: En general se métodos de dinámica empírica no lineal para filtrar el ruido, comprobar la estacionariedad y reconstruir la dinámica del espacio de estados a partir de datos sin ruido. 
- Limpieza de ruido (SSA) 
- pruebas de estacionariedad (Space time separation plot- Time Dalay Embedding)
- Estacionariedad y no linealidad (Surrogate data analysis)
1. Modelación ( ESNN, hiperparametros con Nvidia GPU)
1. Validación del modelo (Indice de eficiencia de Nash-Sutcliffe (NSE))

## Arquitectura del modelo:
El modelo utilizado fue *Echo State Neural Networks (ESNN*), que es un tipo de red neuronal recurrente (RNN) diseñada para procesar y modelar dinámicas temporales complejas de manera eficiente.

Se empleó la infraestructura UF-NVIDIA-GPU para muestrear uniformemente una amplia red de hiperparámetros de ESNN
## Datos de entrada y de salida: 
Entrada: Datos de humedad del suelo preprocesados (cm³/cm³) con una resolución temporal de 1 h.

Salida: Datos de humedad del suelo resultado de predicciones
## Funciones de error: 
Indice de eficiencia de Nash-Sutcliffe (NSE), que analiza la similitud entre las predicciones del modelo y los datos reales, donde los valores cercanos a 1 indican una mejor predicción.
## Entrenamiento: 
- División de los datos en conjuntos de entrenamiento y prueba.
- Se empleó la infraestructura UF-NVIDIA-GPU para muestrear uniformemente una amplia red de hiperparámetros de ESNN

## Resultados importantes:
- Las ESNN lograron predecir las dinámicas de humedad del suelo a partir de las dinámicas reconstruidas, tanto en los datos de entrenamiento como en los datos fuera de muestra
- Las ESNN fueron capaces de diferenciar entre eventos extremos recurrentes y eventos aleatorios de humedad del suelo.
- La combinación de técnicas de dinámica no lineal empírica con ESNN redujo la complejidad computacional
- Se logró reconstruir dinámicas no lineales deterministas de baja dimensión en los registros de humedad del suelo de los sensores
- Se logró un NSE de 0.93 y 0.99

## Fortalezas del paper:
- Disponibilidad de datos con alta resolución temporal 
- ESNN consume requiere de menos capacidad computacional
- Se lograron predicciones muy buenas con un NSE de 0.93 y 0.99
- Demuestra como se puede trabajar con datos no lineales que pueden estar controlados por factores deterministas ambientales, climáticos y topológicos

Huffaker, R., Muñoz-Carpena, R., & Migliaccio, K. W. (2024). Sensor records can be used to forecast complex soil moisture dynamics with symbiosis of empirical nonlinear dynamics and echo state neural network AI. *Computers and Electronics in Agriculture*, *222*. <https://doi.org/10.1016/j.compag.2024.109031>

# Paper 2
## Título: 
A Comprehensive Study of Deep Learning for Soil Moisture Prediction
## Autores: 
Yanling Wang, Liangsheng Shi, Yaan Hu, Xiaolong Hu, Wenxiang Song, y Lijun Wang.
## Ideas Principales: 
- Predecir con precisión la humedad del suelo presenta retos debido a la no linealidad del transporte de agua del suelo y a la variabilidad de las condiciones.
- Deep Learning ha surgido como un enfoque prometedor para simular la dinámica de la humedad del suelo
- El análisis Shapley (SHAP) Additive Explanations es un enfoque utilizado para interpretar modelos de aprendizaje automático y obtener explicaciones sobre cómo cada característica de entrada contribuye a las predicciones realizadas por un modelo, en el articulo se usó para para comprender cómo los modelos aprovechan los datos y entender patrones.
- Se analizan modelo 10 modelos, 3 puros y 7 híbridos, de los cuales 6 nunca habían sido usado en modelos de humedad del suelo
- Las CNN pueden extraer información temporal local de los datos deslizando núcleos convolucionales a lo largo de la dimensión temporal, por otro lado, las RNN destacan en la captura de la información global de la secuencia temporal
- Las estrategias de entrenamiento específicas con estructuras de red adecuadas pueden mejorar el rendimiento de la predicción, por ejemplo, las GAN permiten que el objetivo de entrenamiento de las redes neuronales vaya más allá de minimizar el error cuadrático medio de los datos y utilizar el entrenamiento adversarial para captar plenamente las regularidades de los datos.
## Datos:
- Datos in situ de humedad del suelo recopilados en 30 disitintos lugares del mundo provenientes de la red de *International Soil Moisture Network (ISMN),* con datos de hasta 22 años.
- Datos de precipitación, temperatura atmosférica, radiación de onda larga y corta, velocidad del viento y humedad relativa, provenientes del proyecto NASA POWER.
## Metodología
- Recopilación de datos a escala global 
- Corrida de modelos: Se compararon modelos tradicionales de aprendizaje automático (RF, ELM, SVR) y de aprendizaje profundo (CNN, LSTM, Transformer) con arquitecturas híbridas (e.g., CNN-LSTM, FTA-LSTM).
- Evaluación de modelos: Coeficiente de determinación (R²) y error cuadrático medio (RMSE).
## Arquitectura de los modelos: 
Machine learning models:** random forest (RF), extreme learning machine (ELM), and support vector machine (SVM) machine learning.** 

Random forest, se utiliza para tareas de regresión y clasificación y ha ganado popularidad por su gran precisión. Extreme learning machine utiliza una red neuronal de una sola capa como base. ELM consigue una velocidad de aprendizaje rápida y una gran capacidad de generalización empleando pesos y sesgos aleatorios en la capa de entrada y aplicando la teoría de la matriz inversa generalizada para calcular los pesos de la capa de salida. Support vector machine se propuso para aplicaciones de clasificación y regresión. Su objetivo es encontrar el hiperplano de margen máximo que mejor separa los puntos de la muestra.

Basic deep neural networks: LSTM, CNN y Transformers

LSTM, pueden superar el problema de la desaparición del gradiente del las RNN y memorizar más información útil a través de una unidad especial llamada cell state. CNN, se aplicaron originalmente al reconocimiento de imágenes. Las capas de convolución y agrupación de las CNN pueden extraer las características distintivas de los datos dados y reducir al mismo tiempo el número de datos que hay que procesar. Transformer, el mecanismo de autoatención puede modelar las dependencias y agregar características a partir de las entradas. Por lo tanto, una estructura de apilamiento de mecanismos de autoatención como Transformer (Vaswani et al., 2017) puede lograr las funciones de las CNN y las RNN sin iteraciones

Hybrid deep learning models: Hybrid structure of CNN and LSTM, Hybrid structure of attention and LSTM

Hybrid structure of CNN and LSTM**,** estos modelos híbridos poseen capacidades avanzadas para manejar diversos tipos de datos, lo que suele mejorar la precisión de las predicciones. Hybrid structure of attention and LSTM, Sirven para mejorar la precisión de los modelos de aprendizaje profundo y abordar el problema de la falta de interpretabilidad, se han incorporado mecanismos de atención a los modelos LSTM para ponderar la importancia de las diferentes dimensiones de los vectores de entrada y salida.

GAN-LSTM

Los GAN (Goodfellow et al., 2014) constan de un generador y un discriminador. El generador está diseñado para generar predicciones similares a la verdad, mientras que el discriminador intenta distinguir entre la verdad y las predicciones, muy eficaces en diversos campos, especialmente en la predicción difusa.
## Datos de entrada y salida:
Entrada: Datos de los últimos 4 días de:

- humedad del suelo.
- Precipitación
- temperatura del suelo 
- radiación de onda corta y larga
- velocidad del viento
- humedad relativa

Salida: Predicción de la humedad del suelo para el quinto día.

## Función de error:
- Error cuadrático medio (RMSE) para las predicciones.
- En GAN-LSTM con el discriminador
## Entrenamiento
- División de datos: 60% para entrenamiento, 20% para validación y 20% para pruebas.
- Hiperparámetros en la función de pérdida de GAN es crucial
## Resultados importantes:
- El modelo long short-term memory (LSTM) es muy adecuado para las predicciones de humedad del suelo
- El mejor Accuaracy fue logrado con feature attention LSTM (FA-LSTM) y the generative-adversarial-network-based LSTM (GAN-LSTM)
- La visualización de la incrustación estocástica de vecinos distribuida en t (t-SNE) ilustra las diferencias en las características codificadas entre los distintos modelos
- Los coeficientes de autocorrelación para el contenido de agua del suelo a diferentes profundidades disminuyen al aumentar el número de días de retraso.
## Fortalezas del paper:
- Tienen gran cantidad de datos, con diversas características topográficas que son tenidas en cuenta.
- Estudian los resultados de la predicción de la humedad con distintos modelos de Machine Learning .
- Se utilizan modelos de basic feature e hibridos
- Seis de los modelos se aplican a la predicción de la humedad del suelo por primera vez
- Se comparan sistemáticamente las capacidades predictivas y los costos computacionales de los modelos en diferentes texturas y profundidades del suelo.

Wang, Y., Shi, L., Hu, Y., Hu, X., Song, W., & Wang, L. (2024). A comprehensive study of deep learning for soil moisture prediction. *Hydrology and Earth System Sciences*, *28*(4), 917–943. <https://doi.org/10.5194/hess-28-917-2024>
# **Paper 3**
## Título: 
Soil moisture forecast for smart irrigation: The primetime for machine learning
## Autores: 
Rodrigo Togneri, Diego Felipe dos Santos, Glauber Camponogara, Hitoshi Nagano, Gilliard Custódio, Ronaldo Prati, Stênio Fernandes, Carlos Kamienski**.**
## Ideas principales
- El auge del Internet de las Cosas ha permitido obtener datos de humedad del suelo de mayor resolución espaciotemporal mediante sensores in situ.
- La abundancia de datos permite la predicción de la humedad del suelo basada en el aprendizaje automático como alternativa a los enfoques tradicionales para la estimación.
- Se predicen los valores mínimo y máximo de los días siguientes.
- LightGBM tiene mejores resultados en la predicción de humedad del suelo respecto a la regresión lineal, arboles de decisión, random forest, LSTM y StemGNN.
- La predicción de la humedad del suelo alcanza su máximo rendimiento considerando únicamente la humedad pasada del suelo, un índice contextual y una predicción de precipitaciones.
## Datos
- Los datos provienen de sensores de Agrosmart3, un proveedor brasileño de riego inteligente. Son tomados de regiones con distintas características de cobertura, topográfica y climática. Los datos son capturados a distintas profundidades en el suelo (profundidades de 20 cm, 40 cm, 60 cm)
- Otros datos de los sensores: temperatura, radiación solar, humedad relativa, velocidad del viento, precipitación. 
- Datos de pronósticos meteorológicos.

## Metodología 
- División del conjunto de datos: Entrenamiento (70%), validación (20%) y prueba (10%)
- Inclusión de características basadas en datos contextuales mediante autoencoders para capturar comportamientos atípico.
- Aplicaciónde algoritmos de aprendizaje automático (LightGBM, bosques aleatorios (RF), redes neuronales recurrentes (LSTM, StemGNN), y perceptrón multicapa (MLP)
- Evaluación de modelos (RMSE, MAE y MAPE)

## Arquitectura del modelo: 
Modelos: LightGBM, bosques aleatorios (RF), redes neuronales recurrentes (LSTM, StemGNN), y perceptrón multicapa (MLP).

Para los conjuntos de árboles de decisión, se eligió RF como representante del tipo de predictores independientes y LightGBM como representante del tipo de predictores secuenciales. Elegimos LSTM y StemGNN como representantes de los enfoques RNN, que dieron resultados competitivos en problemas de series temporales. Se eligió StemGNN también porque mostró gran rendimiento en series tmeporales. N-BEATS es un algoritmo que ha demostrado previamente superar a los ganadores de M4 en los conjuntos de datos de M4. Por último, se añadió MLP como otra línea de base, un enfoque estándar de redes neuronales artificiales (ANN), sin el componente de recurrencia.

Autoencoder**:** captura el comportamiento típico intradiario de la humedad del suelo para calcular el error medio de cada día frente a este comportamiento típico. Se usó para para análisis de contextos anómalos.
## Datos entrada y salida:
Entrada: Datos de humedad, temperatura, radiación solar, humedad relativa, velocidad del viento, precipitación y datos de pronósticos meteorológicos

Salida: Predicción de valores mínimos y máximos diarios de humedad del suelo en las próximas 48 horas.
## Función de error:
Error cuadrático medio (RMSE), MAE (error absoluto medio), R² ajustado y MAPE (error porcentual absoluto medio).
## Entrenamiento: 
- Optimización de hiperparámetros utilizando la biblioteca *scikit-optimize*.
- División del conjunto de datos: Entrenamiento (70%), validación (20%) y prueba (10%)
## Resultados importantes: 
- LightGBM logró la mayor precisión con un R² ajustado entre 0.94 y 0.98 para predicciones diarias.
## Fortalezas del paper: 
- Alta resolución temporal de los datos, teniendo datos horarios mediante IOT.
- Características de las zonas en donde se encuentran instalados los sensores, lo que permite generalizar los resultados de los modelos.
- Mediciones de humedad a distintas profundidades (profundidades de 20 cm, 40 cm, 60 cm).

Togneri, R., Felipe dos Santos, D., Camponogara, G., Nagano, H., Custódio, G., Prati, R., Fernandes, S., & Kamienski, C. (2022). Soil moisture forecast for smart irrigation: The primetime for machine learning. *Expert Systems with Applications*, *207*. https://doi.org/10.1016/j.eswa.2022.117653
# Paper 4
## Título: 
Comparing modern and traditional modeling methods for predicting soil moisture in IoT-based irrigation systems
## Autores: 
Gilliard Custódio, Ronaldo Cristiano Prati.
## Ideas principales: 
- Dentro de los modelos de ML, Random Forest fue el modelo más eficiente y estable.
- Este estudio utilizó modelado de series temporales mediante ML y modelos estadísticos como ARIMA, NAIVE
- Algoritmos estadísticos útiles para predicción de series de tiempo Naive, Vector Autore-gression (VAR), Exponential Smoothing (ES) [19], and Autore-gressive Integrated Moving Average (ARIMA). Donde ARIMA demostró ser el mejor para la predicción de humedad.
## Datos: 
Datos de humedad del suelo utilizando dos años de datos que se obtienen mediante sensores con tecnología de IOT, incluyendo factores como la humedad del suelo, temperatura y clima.

Los datos provienen de dos fuentes: Red Internacional de Humedad del Suelo (ISMN) y Cook Agronomy Farm (CAF) de Estados Unidos.

CAF: 42 sensores: Each sensor records SM, temperature, and bulk electrical con-ductivity at five depths: 0.3, 0.6, 0.9, 1.2, and 1.5 meters. Los datos incluyen: Daily temperature and rainfall data from the near-est meteorological station.

ISMN: 10 datasets de distintas partes del mundo, incluyendo CAF. Contiene datos de humedad del sulo, temperatura del suelo, temperatura del aire y precipitación.
## Metodología:
La metodología en general, utiliza ventanas móviles para el entrenamiento y validación, con una optimización de hiperparámetros en la primera fase, y evaluaciones de desempeño utilizando métricas como MAE, RMSE y MAPE y se finaliza con una comparación de resultados. A continuación se describe con mayor detalle cada paso:

División del conjunto de datos:** El conjunto de datos se dividió en dos períodos de un año. El primer período se utilizó para optimizar los hiperparámetros de los modelos, mientras que el segundo período se usó para la validación.

Se utilizó un formato de ventana móvil sobre el primer período de datos para el entrenamiento.

El conjunto de prueba se definió como el 25% del tamaño del conjunto de entrenamiento.

Se optimizan los hiperparámetros y se registran los valores de predicción de la serie para calcular las métricas de evaluación (MAE, RMSE, MAPE).

Para cada predicción diaria, se utilizan los datos de los días anteriores y, después de 30 días, se vuelve a ajustar el modelo. También se realizó otra corrida utilizando 15 días.

Se seleccionó el mejor modelo estadístico y el mejor modelo de ML.
## Arquitectura del modelo: 
- **Random forest:** Es una técnica de ensamblaje derivada del bagging, Consiste en **n** predictores construidos a partir de **árboles de decisión**, introduciendo **selección aleatoria de variables** durante la construcción de los predictores. Permitiendo que el algoritmo se entrene con conjuntos de entrada diversos, lo que reduce la **varianza de los predictores** y mejora la **exactitud de la predicción final**.
- **Extreme Gradient Boasting:** Es una implementación de **Gradient Boosting Machines** que utiliza **árboles de decisión** como predictores débiles.
- N-BEATS: Es una arquitectura diseñada para la **predicción de series temporales univariantes**. Consiste en **M apilamientos**, que funcionan como un modelo de ensamblaje similar al boosting.
- **Spectral Temporal Graph Neural Network (StemGNN)**:  Combina Transformada Discreta de Fourier Gráfica (GDFT), Transformada de Fourier Discreta (TFD), y componentes de aprendizaje profundo. La matriz espectral se filtra a través de una red neuronal convolucional en grafos.
## Datos de entrada y salida: 
- Entrada: Variables de humedad del suelo (a diferentes profundidades), temperatura del aire y precipitación.
- Salida: Predicción diaria de humedad del suelo a corto plazo..

## Entrenamiento: 
- Uso de ventanas móviles para entrenar y validar modelos en diferentes intervalos de tiempo.
- Optimización de hiperparámetros mediante selección iterativa.
- El conjunto de entrenamiento se definió como el 80% de los datos y el conjunto de prueba el 20%. 
- Ajustes periódicos cada 15 o 30 días para evaluar estabilidad y precisión.

## Función de error: 
Error absoluto medio (MAE), error cuadrático medio (RMSE) y error porcentual absoluto medio (MAPE).
## Resultados importantes:
- ARIMA fue el modelo más preciso en 8 de 10 experimentos, superando a modelos de ML como StemGNN.
- Los algoritmos univariados fueron más eficientes en la mayoría de los casos, lo que sugiere que las variables exógenas aportan poco a la predicción.
## Fortalezas del paper:
- Se tienen usan  diferentes modelos como de machine learning: Extreme Gradient Boosting (XGM) and Random Forests (RF), Deep Learning’s Spectral Temporal Graph Neural Network (StemGNN), and Vector Autoregression. 
- Modelos estadísticos: Statistical algorithms included Naive [19], Vector Autore-gression (VAR) [20], Exponential Smoothing (ES) [19], and Autore-gressive Integrated Moving Average (ARIMA) 
- Incluye factores como** humedad del suelo, temperatura y clima
- Se analizan algoritmos multvariantes y univariantes.
- Se investiga el tamaño de muestra ideal requerido para construir un modelo eficiente, considerando diferentes escenarios de disponibilidad de datos que van de uno a doce meses o más
- Se compara el rendimiento de algoritmos univariantes y multivariantes en diez conjuntos de datos de diversas regiones del mundo
- Busca proporcionar información sobre el rendimiento de diferentes algoritmos de pronóstico de humedad del suelo e identificar los algoritmos más eficientes para ello.

**Custódio, G., & Prati, R. C. (2024). Comparing modern and traditional modeling methods for predicting soil moisture in IoT-based irrigation systems. *Smart Agricultural Technology*, *7*. [https://doi.org/10.1016/j.atech.2024.100397**](https://doi.org/10.1016/j.atech.2024.100397)**

# Paper 5
## Título:
** From data to interpretable models: machine learning for soil moisture forecasting
## Autores: 
Aniruddha Basak, Kevin M. Schmidt, Ole Jakob Mengshoel
## Ideas principales: 
- Los modelos Accumulative Representation (NAR) and the Additive Exponential Accumulative Representation (AEAR) son modelos basados en datos y se enfocan en la hidrología determinista y física. Los parámetros aprendidos del modelo representan los procesos de redistribución hidrológica no saturada basados físicamente en la gravedad y la succión.
- El análisis de los datos es complicado por el rápido cambio de la geomorfología observada en las laderas en respuesta incluso a precipitaciones de pequeñas a moderadas.
- LSTM se utiliza como un modelo de referencia moderno para predicción de humedad del suelo. Su capacidad para manejar dependencias temporales lo hace adecuado para problemas de series temporales complejas, como la humedad del suelo en respuesta a eventos de lluvia.
- Se señala que los modelos para la humedad del suelo deben ser interpretables (parámetro interpretables por especialistas en ciencias de la tierra), basados en datos y que tenga predicciones precisas y aplicables en un lapso de 5 a 24 horas.

## Metodología
Inicialmente se sigue la metodología para lo siguientes modelos

**NAR Y EAR:** 

1. Mediciones de humedad del suelo y precipitación
1. Pronóstico de condiciones futuras del suelo: Se emplea un modelo hidrológico con predicciones de precipitación y el contenido actual de agua en el suelo.
1. Preprocesamiento de los datos: Se hace un submuestreo para reducir la demanda computacional.
1. Entrenamiento del modelo  hidrológico en función de la precipitación y el tiempo.
1. Validación: se valida si los parámetros estimados son consistentes con las propiedades del suelo y se ajustan a la realidad de los datos.

**LSTM:**

1. Mediciones de humedad del suelo y precipitación
1. Optimización y ajuste de parámetros: se ajustan los parámetros de la red utilizando el optimizador Adam.

Posteriormente se comparan las métricas para entender cuál fue el mejor modelo.

## Arquitectura del modelo: 
Modelos basados en datos: **Accumulative Representation (NAR) and the Additive Exponential Accumulative Representation (AEAR)**

- NAR: Modelo acumulativo basado en tasas de secado (kd) y humedecimiento (kw), con constantes físicas ajustadas.
- AEAR: Extensión de NAR que incorpora sumas de exponenciales para capturar dinámicas complejas.

**LSTM** se utiliza como un modelo de referencia moderno para predicción de humedad del suelo. Su capacidad para manejar dependencias temporales lo hace adecuado para problemas de series temporales complejas, como la humedad del suelo en respuesta a eventos de lluvia.
## Datos de entrada y salida: 
- Entrada: Datos históricos de humedad del suelo y lluvia acumulada.
- Salida: Predicciones de humedad del suelo para horizontes de 5 a 24 horas.
## Entrenamiento: 
En general se siguieron los siguientes pasos para el entrenamiento de los modelos: 

- Preprocesamiento de los datos mediante submuestreo.
- División en datos de entrenamiento y prueba.
- Optimización y ajuste de parámetros mediante ADAM
## Función de error: 
- Optimización: Minimización del error cuadrático medio (MSE).
- Además se corrieron las siguientes métricas: Error absoluto medio (MAE), error cuadrático medio (RMSE) y error porcentual absoluto medio (MAPE).
## Resultados: 
- Los modelos NAR y AEAR propuestos han demostrado, en experimentos de previsión, ser competitivos con varias líneas de base establecidas y de última generación.
- El modelo AEAR se ajusta bien a los datos para tres texturas de suelo distintas a profundidades variables por debajo de la superficie del suelo (5, 15 y 30 cm).
- El modelo AEAR incluye parámetros hidrológicos y proporciona previsiones más precisas que los modelos existentes para horizontes temporales de 10-24 h. Estos periodos son útiles para alertas de ocurrenciade fenómenos amenazates como como inundaciones y movimientos en masa.
- Los modelos LSTM(2) y LSTM(4) lograron los mejores resultados en términos de error absoluto medio porcentual (MAPE), con valores de 9.8% y 6.3%, respectivamente, superando a otros enfoques como SEM y ARMAX.
- LSTM mostró inestabilidad durante eventos de lluvia prolongada o en pendientes pronunciadas de las curvas de humedecimiento y secado. Esto llevó a errores máximos elevados en comparación con AEAR, lo cual es crítico en aplicaciones como la predicción de deslizamientos.
- AEAR supera a LSTM en consistencia y precisión para horizontes largos (10–24 horas), con un MAPE menor (<10%) y errores máximos más bajos en todos los escenarios.
- El artículo sugiere que combinar las fortalezas de AEAR (robustez y consistencia) con las capacidades de modelado de secuencias de LSTM podría ofrecer un enfoque más equilibrado y robusto para la predicción de humedad del suelo.
- Se observa que los modelos LSTM con h=2h = 2h=2 y h=4h = 4h=4 tienen un mejor desempeño que otros modelos LSTM.
## Fortalezas del paer::
- Se evalúa el rendimiento del modelo utilizando datos de humedad del suelo obtenidos en experimentos controlados de laboratorio.
- Validación de los modelos propuestos de humedad del suelo en campo.
- Simulación de la respuesta de la humedad del suelo tras un incendio con un experimento controlado.

Basak, A., Schmidt, K. M., & Mengshoel, O. J. (2023). From data to interpretable models: machine learning for soil moisture forecasting. *International Journal of Data Science and Analytics*, *15*(1), 9–32. https://doi.org/10.1007/s41060-022-00347-8
# Retos y futuras direcciones
Un reto importante en la predicción de la humedad del suelo es la optimización de hiperparámetros en los modelos de Machine Learning, si bien enfoques se han usado distintas técnicas como ADAM, *scikit-optimize*, ESNN y demás, aún existe una necesidad de estrategias que respondan mejor a la naturaleza heterogénea y no lineal de los datos de humedad del suelo. 

Los artículos revisados indican que el rendimiento de modelos tanto físicos como de ML pueden variar significativamente según la configuración de los parametros y la calidad de los datos de entrada. En este contexto, una futura dirección de investigaciones podría incluir métodos híbridos que combinen técnicas basadas en conocimiento físico y ML, lo que permitiría aprovechar las características intrínsecas de los sistemas hidrológicos, reduciendo el riesgo de sobreajuste y mejorando la generalización en distintos escenarios, sobre todo en una zona como VdeA que con tiene gran variedad de geoformas y tipos de suelo.

Lo anterior, le apunta a un aspecto fundamental que es abordar la falta de interpretabilidad de los modelos puramente de ML, que a menudo son percibidos como "cajas negras".
# Conclusiones
El avance en la predicción de la humedad del suelo se evidencia mediante la  combinación de modelos estadísticos, de aprendizaje automático (ML) y de aprendizaje profundo (DL). Los modelos tradicionales como ARIMA y NAIVE destacan por su simplicidad y capacidad para escenarios univariantes, mientras que LightGBM y Random Forest han mostrado eficiencia y estabilidad en contextos multivariantes. Por otro lado, modelos basados en redes neuronales como LSTM y StemGNN aportan herramientas más sofisticadas para el manejo de series temporales complejas, aunque presentan limitaciones en eventos extremos y mayor consumo computacional. Los modelos como AEAR y NAR, que combinan principios físicos y data-driven, han demostrado ser particularmente útiles al incluir parámetros hidrológicos interpretables y obtener resultados más precisos en un rango de tiempo de 10 a 24 horas.

Por otro lado, la combinación de enfoques empíricos no lineales con arquitecturas como las redes neuronales de ecoestado (ESNN) y las GANs ha permitido reconstruir dinámicas no lineales, diferenciando eventos recurrentes de los aleatorios. Además, el uso de técnicas como SHAP para interpretar modelos ayuda a que estas herramientas no sean "cajas negras", lo cual es importante para la adopción en sistemas de alerta temprana y toma de decisiones en la GRD.
# Preguntas
- ¿Cómo mantener el equilibrio entre mayor precisión y optimización en la computacional requerida?
- ¿Qué enfoques consideran más efectivos para garantizar que los modelos de aprendizaje profundo sean interpretables y aceptables?
- ¿Qué desafíos técnicos se tienen al combinar modelos de ML con modelos hidrológicos físicos?
- ¿Qué estrategias son más eficientes para la calidad de datos ruidosos o incompletos provenientes de sensores?
- ¿Cómo podrían integrarse estos modelos basados en datos de Sensores In Situ con datos de satélites como SMAP?
