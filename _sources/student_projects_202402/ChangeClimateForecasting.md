# Change climate forecasting: Lierature Review 

## Introduction
Climate change results from long-term shifts in temperatures and weather patterns, driven by anthropogenic or natural factors. Global warming, primarily caused by greenhouse gas emissions (e.g., CO2, CH4), has accelerated the pace of these changes, leading to rising temperatures, increased droughts, and more frequent extreme weather events. Consequently, climate change forecasting is crucial for urban long-term planning, mitigating climate emergencies, and protecting ecosystems.

Effective climate change forecasting requires innovative approaches to better understand its dynamics and develop practical strategies for adaptation and mitigation. Machine learning and deep learning techniques are increasingly utilized across various fields, particularly in climate studies. Tools such as LSTMs, CNNs, gradient boosting (GB), and hybrid methods provide technical and practical solutions for climate change prediction by leveraging data quality, computational efficiency, and the complexity of physical processes.


## Paper Reviews

## Paper 1. Exploring the land-use urban heat island nexus under climate change conditions using machine learning approach: A spatio-temporal analysis of remotely sensed data
- **Authors:** Priyanka Rao, Patrizia Tassinari, Daniele Torreggiani. (2023).
- **Key Highlights:**
   - It explores how land use and land cover (LULC) transformation contributes to surface temperature (LST) and the intensification of urban heat islands (UHI).
   - It employs a machine learning model (Gradient Boosting Regression) to analyze the contributions of individual factors to the increase in surface temperature (LST).
- **Data used:**
   - The temporal data from Landsat 5 (1991–2011) and Landsat 8 (2013–2021)
The regional geoportal of Emilia-Romagna region provides land use maps at a spatial resolution of 1.5 ha from 1976 to 2017
- **Methodology:**
   - Model Architecture: The scikit-learn Python package was used to implement ML techniques and explore the relationship between land cover variables and summer season LST variation over multiple years. Specifically, gradient boosting (GB) regression model
   - Inputs and Outputs: The model takes the land use indices (NDVI, NDBI, NDWI, NDBAL) and calculates the impact on soil temperature (LST) and the location of heat islands (UHI).
   - Loss Function: Employed a combination of mean squared error (MSE) and structural similarity index (SSIM) to ensure both pixel accuracy and structural fidelity.
   - Training: The model was trained and tested using an 80:20 ratio.
- **Key results:** 
   - This study utilizes advanced GEE platform to estimate LST and land use indices using long-term earth observation data, focusing on intra-urban trends in small urban area
   - The ML model employed in this study effectively captures the complex relationship between land cover indices and LST.
- **Machine Learning Tool Used:** 
   - Gradient Boosting Regression Model (GB): GB regression has been widely effective in various fields due to its boosting method and shallow trees, which prevent overfitting
   - Hyperparameters were optimized to obtain the best-fit model with high accuracy.
- **Strengths:** 
   - The combination of satellite data and ML provides a better understanding of complex temperature patterns in urban environments.
   - The study is significant for small municipalities settings like Imola, where urban planning decisions impact the local climate.
-**Limitations:** 
   - The study is focus solely on daytime surface temperatures and lack of consideration for diurnal variability.

## Paper 2. Study of Climate Change Detection in North-East Africa Using Machine Learning and Satellite Data.
- **Authors:** Sara K. Ibrahim, Ibrahim E. Ziedan, and Ayman Ahmed. (2021)
- **Key Highligts:** 
   - The use of machine-learning (ML) models based on essential climate variables (ECVs) to investigate the relationship between the GHGs and the rhythm of climate variable change.
- **Data Used:** 
   - Satellite data (SCIAMACHY/ ENVISAT (nadir mode) and TANSO/GOSAT) produced by the U.K. NCEO and reanalysis dataset from ERA5. Temporal data (2003 – 2018)
- **Metodology:** 
   - Model Architecture: H-CNN (Multiheaded Convolutional Neural Network), Autoencoders (LSTM and CNNLSTM), long short-term memory (ConvLSTM).
   - Inputs and Outputs: Temperature, CO2, CO4, Pressure, total column water vapor (TCWV), and total column rainwater (TCRW) as input and prediction of climate variables: temperature, CO2, CH4 as outputs.
   - Training: Split the data into standard weeks, by organizing the data into weeks gives 677 full standard weeks for training a predictive model, whereas the test dataset has 156 weeks.
- **Key Results:** 
   - The multihead CNN and autoencoder could be used effectively to predict climate variables compared with other neural networks such as traditional.
   - The multihead CNN achieved the highest accuracy in linking between the temperature as the main climate variable from one side and CH4 and CO2 as GHG factors from the other side.
- **Machine Learning Tool Used:** 
   - Long short-term memory (LSTM), convolutional neural network (CNN) (multiple input channels and multiple input heads), and autoencoders (LSTM, CNNLSTM, and CONVLSTM).
- **Strengths:** Models such as multi-head CNN (H-CNN) achieve high accuracy in metrics such as RMSE and R², showing significant correlations between climate variables.
- **Limitations:** ML models can fit observations very well, but predictions may be physically inconsistent due to observational biases.

## Paper 3. Climate change prediction by combination prediction method based on deep learning models
- **Authors:** Amin Amiri, Yu Liang, Mbakisya Onyango. (2023)
- **Key Highligts:** Construction of a model based on EMD-RVM to predict the future changes of climate.
- **Data Use:**
   - Mauna Loa Observatory, Scripps Research Institute Carbon Dioxide Project
   - Temporal data: 1988-2018
- **Metodology:**
   - Model Architecture: EMD decomposition. Decompose the quantized climate change values by EMD to obtain multiple decomposition components. And The RVM prediction method is applied to each component obtained after decomposition
   - Inputs and outputs: fossil fuel combustion, land use, sharp decline in forest resources, population, number of natural disasters, concentration, and ocean temperature as inputs. For the outputs, the magnitude of climate change (numerical value) is predicted for 2019-2043 (future predictions).
   - Loss Function: Mean error, Accuracy, error
- **Key results:**
   - The proposed method can be applied to the prediction of a wide range of time series indicators with non-stationary series, has some applicability and generalizability
- **Machine learning tool used:**
   - Empirical modal decomposition is applied to decompose the climate change indicators, which can obtain several IMF components
   - Relevance Vector Machine: method to predict each IMF component and reconstruct the overall climate change trends
- **Strengths:** EMD allows decomposing volatile data into more manageable components, improving the predictive capability of the model.
- **Limitations:** The model does not directly incorporate physical principles of the climate system, limiting its scientific interpretability

## Paper 4. Pioneering Climate Forecasting in Tennessee with LSTM-ANN Machine Learning Model
- **Authors:** Amin Amiri, Yu Liang, Mbakisya Onyango. (2023).
- **Key Highlights:**
   - Use of a hybrid machine learning model based on LSTM (Long Short-Term Memory) and ANN (Artificial Neural Network) to predict temperature and precipitation patterns in Tennessee.
   - Combines short-term and long-term analysis of historical climate data with high accuracy in future predictions.
-**Data used:**
   - Historical temperature and precipitation data obtained from the Modern-Era Retrospective Analysis for Research and Applications (MERRA), spanning the period from 1980 to 2022, with an hourly temporal resolution.
- **Methodology:**
   - Architecture: The model is a hybrid combination of LSTM (Long Short-Term Memory) and ANN (Artificial Neural Network), composed of five consecutive LSTM layers with final ANN layer.
   - Training: Temperature and precipitation data was trained and tested for prediction purposes. The training phase utilized data from January 1980 to December 2015, while the testing phase covered the period from 2015 to 2022.
- **Strengths:**
   - Combines LSTM and ANN to capture complex temporal patterns in climate data.
   - Integrates short-term and long-term analyses with high accuracy in future predictions.
- **Limitation:**
   - The model is specifically designed for Tennessee, limiting its applicability to regions with different climate patterns

## Paper 5. Neural Network Structure for Tracking the Climate Temperature Change
- **Authors:** Irina Topalova, Pavlinka Radoyska
- **Key Highlights:**
   - The method does not require complex computations, as they are replaced by a single training of a large volume of data and multiple iterations of neural network training
   - The union of SOM and MLP models
- **Data used:**
   - Kaggle (GlobalLandTemperaturesByCity dataset)
   - Variable: Monthly average temperatures for two periods: 1997-1999 and 2011-2013.
- **Methodology:**
   - Architecture: Groups climate data into classes based on similarities in temperature changes over a 10-year period. (SOM) and classifies these pre-grouped data to assess temperature changes at nearby geographical points during specific time periods (MLP).
   - Loss Function: To evaluate the performance of the MLP neural network, root mean square error (RMSE)
- **Key Results:**
   - Combine neural network models in a common framework to perform automated analysis of trends in temperature changes over selected annual periods for geographically adjacent local regions
Machine Learning Tool Used
   - SOM (Self-Organizing Map): Groups data into classes based on similarities in temperature change patterns over a 10-year period, identifying common trends among geographic data points.
   - MLP (Multi-Layer Perceptron): Classifies the data previously grouped by the SOM for nearby test points during two specific periods: 1997-1999 and 2011-2013, leveraging the SOM-defined classes to assess temperature changes in selected regions.
- **Limitations:** The model needs to be adjusted for other regions with different climatic characteristics.
- **Strengths:** Integrates self-organizing maps and neural networks to handle limited datasets

## Comparison of Approaches
| Methodology/Technique | Key Strengths | Key Limitations | Example Papers |
|-----------------------|---------------|-----------------|----------------|
| Gradient Boosting Regression Model (GB) | Constructs decision trees sequentially to minimize prediction errors | Limited generalization | Rao et al. |
| H-CNN (Multiheaded Convolutional Neural Network) | Significant correlations between climate variables | Predictions may be physically inconsistent due to observational biases | Ibrahim et al. |
| EMD-Relevance Vector Machine | EMD allows decomposing volatile data into more manageable components | The model doesn't directly incorporate physical principles of the climate system | li et al. |
| LSTM - ANN | Capture complex temporal patterns in climate data | Its performance depends on accurate and consistent historical data | Amiri et al. |
| SOM-MLP | Integrates self-organizing maps and neural networks to handle limited datasets | Intensive preprocessing | Irina Topalova, Pavlinka Radoyska |

## Conclusion
Machine learning has significantly improved climate change forecasting methods, enabling more accurate projections with greater speed and reduced computational costs.
However, challenges remain in the application of ML tools to climate modeling. These include integrating the physical processes of climate dynamics into models, generalizing across diverse climate parameters, enhancing long-term predictive accuracy, and incorporating anthropogenic variables.
The development of hybrid models and the refinement of spatial and temporal variables offer promising pathways for advancing global climate change predictions.

## Questions About Methodologies and ML Approaches
- ¿Cuáles son las variables necesarias para el pronóstico de cambio climático?
- ¿Cómo se aplican los autoencoder a los modelos CNN o LSTM?
- ¿Cuál es la función de los Hyperparameters?
- ¿Aplicación de leyes físicas o "leyes numéricas"?
- ¿Son acertados los pronósticos con ML en cambio climático a largo plazo?

## References
1. Priyanka Rao, Patrizia Tassinari, Daniele Torreggiani. (2023) Exploring the land-use urban heat island nexus under climate change conditions using machine learning approach: A spatio-temporal analysis of remotely sensed data. Department of Agricultural and Food Sciences, University of Bologna, 40126, Bologna, Italy. https://doi.org/10.1016/j.heliyon.2023.e18423
2. Sara K. Ibrahim , Ibrahim E. Ziedan, and Ayman Ahmed. (2021). Study of Climate Change Detection in North-East Africa Using Machine Learning and Satellite Data. IEEE JOURNAL OF SELECTED TOPICS IN APPLIED EARTH OBSERVATIONS AND REMOTE SENSING, VOL. 14. DOI 10.1109/JSTARS.2021.3120987
3. Amin Amiri, Yu Liang, Mbakisya Onyango. (2023). Climate change prediction by combination prediction method based on deep learning models. 2023 5th International Academic Exchange Conference on Science and Technology Innovation (IAECST). DOI 10.1109/IAECST60924.2023.10502965 IEEE
4. Amin Amiri, Yu Liang, Mbakisya Onyango. (2023). Pioneering Climate Forecasting in Tennessee with LSTM-ANN Machine Learning Model.  20th International Conference on Smart Communities: Improving Quality of Life using AI, Robotics and IoT (HONET). DOI 10.1109/HONET59747.2023.10374680
5. Irina Topalova, Pavlinka Radoyska. (2023). Neural Network Structure for Tracking the Climate Temperature Change. 2023 International Conference on Computational Science and Computational Intelligence (CSCI). DOI 10.1109/CSCI62032.2023.00030


