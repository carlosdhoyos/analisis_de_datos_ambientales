# Extreme events detection: A Literature Review

## Introduction
Currently, humans face constantly changes that affect their way of living. From a meteorological perspective, extreme rainfall events are a significant factor that challenges the normal conditions of populations, causing damage, significant alterations to their infrastructure and resources, among other impacts. The identification of these events has become a necessity to prepare and warn populations about their magnitudes, permiting improvements in risk management for public policies.

Additionally, the changing conditions generated due to climate change, challenges traditional knowledge and skills, creating a need for the implementation of new technologies and tools that helps the generation of effective results to acomplish these needs. The use of artificial intelligence and machine learning in these processes has transformed how problems are approached, providing tools for data analysis, pattern recognition, and phenomenon modeling. This allows for addressing various variables used to train models from multiple perspectives, offering a much broader spectrum of potential solutions. To implement these technologies in the detection of extreme events, the following academic articles demonstrate the application of these information processing alternatives.

## Paper Reviews

### Paper 1: Machine learning models to complete rainfall time series databases affected by missing or anomalous data
- **Authors:** Andrea Lupi, Marco Luppichini, Michele Barsanti, Monica Bini, 
Roberto Giannecchini
- **Key Higlights:**	- Machine learning models capable of predicting rainfall data starting from the values of the nearest raingauges at one historic time point.	- Influence of the anomalous input data on the prediction of rainfall data.
- **Data used:**	-  Tuscany Region Hydrologic Service (SIR) and contains data acquired from several meteorological stations: automated download procedure through codes written in Python and HTTP protocol. 
- **Methodology:**	- Database and data input pre‑processing: Use only the validated data to minimize errors		- Model architecture: open-source framework Tensorflow. LR model is developed using the scikit-learn framework, implementing two model architectures: CNN-LSTM and ED-LSTM.
- **Key results:** 	- Measurement anomalies in time series cause major errors in deep learning models	- Compareing the model errors with those derived from other methods (Beauchamp et al. 1989; Gyau-Boakye and Schultz 1994; Abebe and Price 2003; Coulibaly and Evora 2007; Caldera et al. 2016; Balcha et al. 2023), recognizing a reasonable comparability, concludes that AI techniques could have higher accuracy than traditional methods
- **Machine Learning Tool Used:**	- Two CNNs layers of 64 and 128 filters (with a kernel size of 2 and stride length of 1), respectively, followed by a Max Pooling layer with size 1, an LSTM layer of 200 units, a dense layer of 50 neurons, and an output layer of one neuron	-  Encoder-decoder LSTM, with two LSTM nodes. Both the encoder and the decoder consist of a pair of sequence layers (LSTM) of 32 and 16 units followed by a repeat vector node for the encoder and 16 and 32 units for the decoder followed in turn by a time-distributed dense node. 
- **Strengths:**	- Evaluation of errors: mean absolute error (MAE) and the average relative error was calculated for each raingauge (RMAE)		- Use of validated data to minimize errors
- **Limitations:**	- Major errors correspond to major differences among the input data or with the output values. The causes of these anomalies can be different. They cannot exclude meteorological factors, but we suppose that the main cause could be linked to raingauges malfunctions, given the specific selection of the input.
- **Relevance to Extreme Event Detection:**	-  This study also demonstrated that the deep learning model performances are strongly influenced by the input data, confirming the data-driven behaviour of

### Paper 2: Deep learning rainfall–runoff predictions of extreme events
- **Authors:** Jonathan M. Frame, Frederik Kratzert, Daniel Klotz, Martin Gauch, Guy Shalev, Oren Gilon, Logan M. Qualls, Hoshin V. Gupta, and Grey S. Nearing
- **Key Higlights:**	- The most accurate rainfall–runoff predictions are currently based on deep learning	- There is a concern among hydrologists that the predictive accuracy of data-driven models based on deep learning may not be reliable in extrapolation or for predicting extreme events. This study tests that hypothesis using long short-term memory (LSTM) networks and an LSTM variant that is architecturally constrained to conserve mass
- **Data used:**	- Catchment Attributes and Meteorology for Large-sample Studies (CAMELS) data set curated by the US National Center for Atmospheric Research (NCAR)	- NLDAS
- **Methodology:**	- Models: Definitios of the models, trained with daily dataset using the same procedures, using minibatchs with size of 256. Trained with CAMELS information. Tarined along 9 water years and test including 10 water years.	- Use of normalized squared-error
- **Key results:**	- The results indicate broadly similar performance between the LSTM and MC-LSTM across most metrics in the two test periods. However, there were small differences. The MC-LSTM generally performed slightly worse according to most metrics and test periods.	- All models had increasingly large average errors with increasingly large extreme events. The LSTM average error was lowest in all of the return period bins. 
- **Machine Learning Tool Used:**	- A pure LSTM	- Physics-informed LSTM that is architecturally constrained to conserve mass
- **Strengths:**	- Predictions made by data-based rainfall–runoff models are more reliable than other types of physically based models, even in extrapolation to ungauged basins.	-  The data-driven models (both the pure ML model and the physics-informed ML model) were better than benchmark models at predicting peak flows under almost all conditions, including extreme events or when extreme events were not included in the training data set.
- **Limitations:**	- The differences between pure ML and physics-informed ML is worth discussing. 	- It is important to understand that there is only one type of situation in which adding any type of constraint (physically based or otherwise) to a data-driven model can add value: if constraints help optimization.
- **Relevance to Extreme Event Detection:** 	- Finding correlations between identify different models and extreme events precipitation-runoff.	- Provides a new área to investigate due to incorrect initial hypotesis, permiting create new paths to studying LTSM and CM-LSTM models.

### Paper 3: Prediction of Occurrence of Extreme Events using Machine Learning
- **Authors:** J. Meiyazhagan, S. Sudharsan, A. Venkatesan and M. Senthilvelan
- **Key Higlights:**	- Utilize the ability of machine learning algorithms to predict the occurrence of extreme events in a nonlinear mechanical system.	- Prediction involves the determination of reliable indicators or measurable observables of extreme events.	- Non-polynomial mechanical system with external forcing, parametric drive and time delayed feedback and examined the prediction of the occurrence of extreme events with the help of ML tools.
- **Data used:**	- Generation of information bases in three parameters, considering 4 cases.	- Do not applied this information to actual
- **Methodology:**	- Mechanical model describing the motion of a freely sliding particle of unit mass on a parabolic wire rotating with a constant angular velocity.	- Performance of models: Confusion matrix True negative (TN) and positive (TP), and False postive (FP) and negative (FN)	- Acuracy ML models is calculated by dividing the total number of correct classifications by the total number of classifications done.	- Precision denotes how often the model predicts the positive results (extreme cases) correctly. In other words, precision is the ratio between the number of true positives and a total number of predicted positive outcomes.
- **Key results:**
- **Machine Learning Tool Used:**	- Logistic Regression	- Support Vector Machine	- Random Forest 	- Multi-Layer Perceptron
- **Strengths:**	- The considerednon-polynomial mechanical system, as far as the prediction of the emergence of extreme events from the parameter values is concerned, one can optimally use the MLP model	-On examining the performance of each model, we found that the performance of the MLP model is high when compared to the other thre
- **Limitations:**	- Do not applies the results to a study case.
- **Relevance to Extreme Event Detection:**	- Brings a solid base of what ML method we could use in our models.

### Paper 4: Extreme Rainfall Events Classification Using Machine Learning for Kikuletwa River Floods
- **Authors:** Lawrence Mdegela, Esteban Municio, Yorick De Bock, Edith Talina Luhanga, Judith Leo and Erik Mannens
- **Key Higlights:**	- Application of different machine learning techniques for detecting and classifying extreme rainfall events in a sub-catchment.	- Identification and classification of extreme rainfall event is a preliminary crucial task towards success in predicting rainfall-induced river floods.	-  This study has emphasized the importance of selecting appropriate performance metrics to evaluate algorithms effectiveness in detecting rare events.
- **Data used:**	- The aim of this work was to classify rainfall intensity (heavy, light, none) based on 6 weather parameters namely temperature (Minimum and Maximum), relative humidity, precipitation, solar, and wind speed. 	- The data from each station were checked for missing values before being merged into a single data set
- **Methodology:**	- All variables were provided by Tanzania Meteorological Agency and the Pangani Basin Water Board(PBWB)	- Dataset: The data from each station were checked for missing values before being merged into a single data set. Data splitted into train and set in 4:1 proportion. There was 6 featyres and 1 target class. 	- Model evaluation: Precision, Recall and F1 score.
- **Key results:**	- The generic Multi-layer Perceptron performs best when identifying the heavy rainfall events	- The use of satellite-based rainfall estimates can enhance rainfall monitoring and prediction in regions where traditional measurement methods are sparse or challenging to implement, albeit with the need for continual improvements in their accuracy and uncertainty estimation.	- The scores from F1_score means both XGBoost and Random forest have perfect precision and recall when you give equal importance to both false negatives and false positives. Clasifing the heavy rains, false negatives were the most important.
- **Machine Learning Tool Used:*	- Random Forest	- eXtreme Gradient Boost	- Support Vector Machine	- k-Nearest Neighbors 	- Multi-layer Perceptron
- **Strengths:**	- These models have potential applications in various fields that require accurate predictions of rare events
- **Limitations:**	- Further research is needed to explore the models’ performance in different settings and under different conditions, such as changes in climate patterns and
data sources. 
- **Relevance to Extreme Event Detection:**	- The study provides insights into the potential of machine learning algorithms in predicting rare events and highlights the need for further research to develop more accurate and robust models. 

### Paper 5: Automatic Detection and Classification of Low-Level Orographic Precipitation Processes from Space-Borne Radars using Machine Learning 
- **Authors:** Malarvizhi Arulraj, Ana P. Barros
- **Key Higlights:**	-  The spatial distribution of predicted precipitation classes within the GPM overpass reflects the complex interactions between storms and topography that determine orographic precipitation regimes.	- For each GPM pixel, the local precipitation class informs on the vertical structure of rainfall microphysics aiming to capture low-level processes missed in GPM DPR reflectivity profiles contaminated by ground-clutter	- Develop and demonstrate a generalized framework for precipitation detection and for predicting the vertical structure of  low-level clouds and fog (LLCF) that is needed to initialize the vertical structure of hydrometeors in the rain-shaft model to improve Quatitative Precipitation Estimation (QPE)
- **Data used:**	- MRMS reflectivity	- NEXRAD 3D reflectivity profiles	- Tbs GMI Level-1C	- GPM Ku-PR	- High-ResolutionRapid Refresh (HRRR) Model
- **Methodology:**	- Data Preprocessing: Authorts identify diferent dataset, analyse cluttering of dataset, extract the information they need acording to each model.	- Models and acuracy: Definition of each model and the acuracy for each one.	- Results evaluation.	- Aplications
- **Key results:**	- Automatic Detection and Classification of Low-Level Orographic Precipitation Processes from Space-Borne Radars using Machine Learning	- Error assessment indicates that GPM Ku-PR miss-detection of precipitation is tightly associated with shallow precipitation	- The proposed convolution neural network algorithm (CNN) allows to extract features from GPM DPR and GMI observations to better characterize the precipitation regime.
- **Machine Learning Tool Used:**	- PCM is a Convolutional Neural Network	- PDM relies Random Forest Classifier using GPM Microwave Imager (GMI)
- **Strengths:**	- The AI framework demonstrated is composed of two sequential models: precipitation detection and precipitation regime classification. The detection model inputs (GPM products and NWP reanalysis from operational forecasts centers) are globally available.	- The detection model is applicable globally to possibly improve the GPM Ku-PR algorithm's detection skill provided that accurate reanalysis data are available.	- The proposed convolution neural network algorithm (CNN) allows to extract features from GPM DPR and GMI observations to better characterize the precipitation regime.
- **Limitations:**	- Skill metrics for both detection and classification models will be location-specific depending on: 1) data availability for Machine Learning and statistical assessment  2) regional characteristics 3) the capability of the NWP reanalysis to capture the dominant precipitation processes at a spatial resolution compatible with GPM Ku-PR measurements.
- **Relevance to Extreme Event Detection:*	- Identify posible source of information based on reanalysis.	- Identify different models which allows to identify and clasify low level orographic proecipitation based on Machine Learning


## Comparison of Approaches
| Methodology/Technique | Key Strengths                   | Key Limitations                   | Example Papers                  |
|------------------------|---------------------------------|-----------------------------------|---------------------------------|
| LSTM        | Higher acuracty tan traditional methods, learn from dependencies to long term, permitting capture complex patterns. | Requieres more time to train, sensible due to measurement abnormalities.    | Lupi et al.         |
| CM-LSTM        | Better results than benchmark models. Includes a physical mass conservation in the process. | Pure LSTM shows better results as CM-LSTM without extreme events training. | Frame et al. |
| MLP | Better results than other ML tools as Logistic regression and Random Forest. Accurate prediction of rare events. They are more flexible. They are able to train a non linear model | Tends to overfitting and need big cuantities of datasets | Meiyazhagan et al. |
| Random Forest: | Accurate prediction of rare events. Resolve the problem of overfitting | Longer times of training, they are more complex. | Mdegela et al. |
| PCM | Allows extract features, they are more flexible. They are capable of introduce uncertainty. | Complex to use, high computational requirements. | Arulraj et al. |

## Challenges and Future directions
	- High quality and high resolutions models based in datset, looking to improve AI and ML tools in the models, looking for more acurate predictions.
	- Improving and optimization training looking for reducing times and computational requirements
	- Allow multiple institutions and populations access to models, looking for investigative developement in regions where this resources may not be availeable.
	- Findings in challenges that can help comunities solve complex problems.
	- Machine learning models that allows adapt to multiple variables and challenges.

## Conclusion
The extreme events detection represent a critical challenge in the face of increasing climate change and its associated risks. Machine learning and artificial intelligence offer excellent tools to fight back these issues taking advantage of data analysis and identification of complex patterns, guiding this problems through effective solutions.

While these technologies represents significant obstacles like improvings data limitations, computational requirements, and the need for adaptability to different enviroments. The integration of AI models with traditional meteorological methods will be a big step to improve how professionals study this phenomenon. 

## Questiones about Methodologies and ML Approaches
1. Data Preparation and Requirements:
	- How does the model requires to introduce input dataset?
	- Does the models require an specific source of information to strat the training process?
	- What volumen of information does the models requires to achieve low uncertainty and avoid overfitting?
	- What kind of preproccesing requieres the information?
	- Are the datasets available to download for free? If not, what barriers exist to replicating the studies?

2. Model Architecture:
	- How does the different models works internally?
	- Does the models have internal uncertainties formulas?

3. Training Process:
	- What loss functions and optimization algorithms were used, and why were they selected?
	- How can i improve models to achieve better results in training process?

4. Evaluation and Validation:
	- Can i replicate multiple metrics for the same results?

5. Reproductibility:
	- Are the code for these papers publicly available? If not, what barriers exist to replicating the studies?
	- How can i know what computional resources does any model requires?

6. Model aplications:
	- How can i know which model has better performance under specific conditions.
	- Are this models capable to study diferent variables under the same concept?

7. Future improvements:
	- Is there any possible way to help the authors of the models with any recomendation?

## References
1.  Lupi, A., Luppichini, M., Barsanti, M., Bini, M., & Giannecchini, R. (2023). Machine learning models to complete rainfall time series databases affected by missing or anomalous data. Earth Science Informatics, 16(4), 3717-3728.
2. Frame, J. M., Kratzert, F., Klotz, D., Gauch, M., Shalev, G., Gilon, O., ... & Nearing, G. S. (2022). Deep learning rainfall–runoff predictions of extreme events. Hydrology and Earth System Sciences, 26(13), 3377-3392.
3. Meiyazhagan, J., Sudharsan, S., Venkatesan, A., & Senthilvelan, M. (2021). Prediction of occurrence of extreme events using machine learning. The European Physical Journal Plus, 137(1), 16.
4. Mdegela, L., Municio, E., De Bock, Y., Luhanga, E., Leo, J., & Mannens, E. (2023). Extreme Rainfall Event Classification Using Machine Learning for Kikuletwa River Floods. Water, 15(6), 1021.
5. Arulraj, M., & Barros, A. P. (2021). Automatic detection and classification of low-level orographic precipitation processes from space-borne radars using machine learning. Remote Sensing of Environment, 257, 112355.