# Bias correction in climate models: A literature review
## Introduction

Global Climate Models (GCMs) integrate principles of physics, chemistry, and biology. They are essential tool for understanding climate systems and future projections and how their diverse processes interact with different variations, like climate change. This makes them indispensable in the planning and decision-making processes. However, especially in regional analysis, GCMs have spatial and temporal limitations when representing hydroclimatic variables, such as precipitation. This reduces the precision of regional impact studies and affects decision-making for sustainable development.

For that, bias correction methods have been used to reduce the uncertainty in the GCM's representation of precipitation. The most common methods have been traditional statistical methods. Still, recent advancements in machine learning (ML) have increased interest in their use in the bias correction process, as highlighted by the five papers reviewed in this document.

## Paper Reviews

### Paper 1: Comparison of Conventional and Machine Learning Methods for Bias Correcting CMIP6 Rainfall and Temperature in Nigeria

- **Authors:** Bashir Tanimu et al.  
- **Key Highlights:**  
    - The study examines the performance of three machine learning-based bias correction (ML BC) methods alongside ten traditional BC approaches, focusing on correcting biases in GCMs simulations of rainfall, Tmx, and Tmn in Nigeria.

- **Data Used:**  
    - Simulations from four CMIP6 GCMs for four shared socioeconomic pathways (SSP126, SSP245, SSP370, and SSP585). The models and their spatial resolutions are:  

      | **GCM**         | **Developing Centre**                     | **Spatial Resolution** |
      |------------------|------------------------------------------|-------------------------|
      | BCC-CSM2-MR      | Beijing Climate Centre, China           | 1.125° × 1.125°        |
      | CMCC-ESM2        | Euro-Mediterranean Centre, Italy        | 0.942° × 1.25°         |
      | MRI-ESM2-0       | Meteorological Research Institute, Japan| 1.125° × 1.125°        |

    - The climate research unit (CRU) monthly rainfall, Tmx, and Tmn datasets for 1975–2014 were used as the reference point.

- **Methodology:**  
    - To align the chosen GCMs with the reference data (CRU) resolution, the GCMs were regridded to a resolution of 0.5° × 0.5° using the bilinear interpolation approach.  
    - Thirteen distinct bias correction (BC) methods were applied to rectify the bias in the regridded GCMs for rainfall, Tmx, and Tmn throughout the period from 1975 to 2014.  
    - The six most promising BC procedures were identified using three statistical metrics: relative standard deviation (rSD), percentage of bias (PBIAS), and normalized root mean square error (NRMSE).

- **Key Results:**
    - Random Forest (RF) was ranked as the best method for reducing bias in climate variables in Nigeria. The better performance of RF may be due to its inherent capacity to handle nonlinear relationships.

- **Machine Learning Tools Used:**
    - **Artificial Neural Network (ANN):** Regression-based statistical techniques used to establish complex, nonlinear relationships between GCM simulated variables (predictors) and local climate variables (predictands). They are trained based on historical data and reduce biases to adjust the error to a minimal value.
    - **Random Forest (RF):** Combines the output of multiple decision trees generated from a bootstrap sample to arrive at a single result.
    - **Support Vector Machine (SVM):** A supervised learning method that aims to identify a function that optimally matches the training data while maximizing the error tolerance margin.

- **Strengths:**
    - Comprehensive comparison of multiple bias correction methods using traditional and machine learning approaches.
    - The study uses climate data with quality control and appropriate metrics to evaluate bias correction (BC) models, improving the spatial resolution of future climate projections.

- **Limitations:**
    - Climate variability across different geographical areas affects model performance, requiring context-specific validations.
    - The quality of validation data and the selection of performance metrics are crucial for reliable results.
    - Further research is needed to develop regional climate impact models and measure uncertainty in climate projections.
    - Evaluating advanced machine learning models, such as LSTM, could improve bias correction in GCMs.

- **Relevance:**
    - This paper addresses inaccurate climate projections in Nigeria by providing effective bias correction methods that improve the reliability of climate data.
    - It emphasizes the importance of evaluating downscaling models in specific contexts to obtain accurate and relevant results for local decision-making.
 

### Paper 2: Machine learning and CORDEX-Africa regional model for assessing the impact of climate change on the Gilgel Gibe Watershed, Ethiopia
- **Authors:** Amanuel Kumsa Bojer et al. 
- **Key Highlights:**
    - This study innovates by coupling ML techniques with the CORDEX-Africa RCM to assess climate change impacts on Ethiopia’s Gilgel Gibe Watershed, improving the accuracy and detail of climate projections.

    - The present study aimed to model and predict potential trends in long-term climate change time series and examine their correlation with fluctuations in the Gilgel Gibe watershed.

- **Data Used:** 
    - Daily rainfall, maximum temperature (Tmax), minimum temperature (Tmin), wind speed, relative humidity, and solar radiation hour data from 4 meteorological stations: Gibe, Omo Nada, Deneba, and Jimma collected by the Ethiopian Meteorological Institute (EMI) from 1993 to 2023.
    - CHRIPS database: soil data, geology data, and Digital Elevation Model (DEM).
    - CORDEX-Africa is a regional climate model that offers downscaled climate projections with finer spatial resolution, detailing temperature, precipitation, and other climate variables.
    - The performance of GCM-driven bias-corrected RCMs in replicating the observed baseline climate and projecting future climate change was assessed using the RCMs MIROC5 and 6(CNRM), CCCma (CanESM), CCLM4 (CNRM), CCLM4 (MPI), and REMO (MPI).

![Imagen 1](modelos.png)

- **Methodology:**
    - Various bias correction methods were evaluated and applied to historical observation datasets from 1993 to 2009 to ensure accurate climate projections.
      1. Linear scaling (LS)
      2. Delta change (DC)
      3. Variance scaling (VS)
      4. Power transformation (PT)
      5. Distribution mapping (DM)
    
    - The hydrological simulation model was constructed using three ML techniques:
        1. Random forest (RF)
        2. CatBoosting (CB)
        3. Extra trees (ET)


![Imagen 2](metodologia.png)

- **Key Results:** 
The Delta Method (DM) was the best for temperature data, and the Power Transformation (PT) for precipitation data.
The CatBoost regression algorithm was selected due to its robust performance in simulating future climate scenarios, accurately predicting precipitation and temperature changes under various emission pathways, handling large datasets, and its ability to handle categorical features common in climate data automatically. 

- **Strengths:** The integration of ML models alongside traditional hydrological models like SWAT in assessing the impact of climate change on the Gilgel Gibe Watershed offers a synergistic approach that enhances the robustness and reliability of the analysis, ultimately providing valuable insights for informed decision-making and sustainable water resource management in the face of climate change.

- **Limitations:** The study acknowledges the inherent biases in climate models and the challenges in accurately capturing all spatial and temporal patterns.
The reliance on historical data may limit the applicability of findings to future conditions, especially under extreme climate scenarios.

- **Relevance:**
    - The findings are crucial for informing water resource management and adaptation strategies in the Gilgel Gibe Watershed,  vital for local agriculture and sustainability.
    - The research contributes to the broader understanding of climate change impacts in Africa, highlighting the need for innovative climate modeling and risk management approaches.


### Paper 3: A comprehensive comparison of bias correction methods in climate model simulations: Application on ERA5-Land across different temporal resolutions
- **Authors:** Pranav Dhawan et al. 
- **Key Highlights:**
  - The research compares statistical and machine learning (ML) methods for bias correction in precipitation and temperature data.
  - It emphasizes the performance of these methods across different temporal resolutions: monthly, daily, and hourly.
  - The study utilizes ERA5-Land reanalysis data, which is noted for its high spatial and temporal resolution.
    
- **Data Used:** Hourly values from both observed datasets and reanalysis ERA5 datasets for the period from 1991 to 2020.


- **Methodology:**

    - The study divided the data into training (1991-2014) and testing (2015-2020) phases.
    -  Statistical methods for bias correction:
        1. Linear Scaling (LS)
        2. Variance scaling (VS)
        3. Quantile Mapping (QM)
        4. Power transformation (PT)
        5. Quantile Mapping (QM)
        6. Multivariate Bias Correction (MBC)
    - Machine Learning for bias correction:
       1. Decision tree regressor (DTR)
       2. EXtreme gradient boosting (XGB)
       3. Support vector regression

- **Key Results:**

    - Machine learning methods, particularly XGB, showed superior performance in temperature bias correction at an hourly scale.
    - The DTR method performed best for precipitation, while MBCp was the most effective for temperature.
    - Statistical methods generally outperformed ML methods in the testing phase, especially for precipitation.

- **Strengths:**

    - The study thoroughly compares various bias correction techniques, contributing valuable insights into their effectiveness.
    - It addresses the challenges of complex mountainous orography in the study region.
    - The use of high-resolution ERA5-Land data enhances the reliability of the findings.

- **Limitations:**

    - The performance of models showed degradation during the testing phase, indicating potential overfitting in some cases.
    - The study's findings may be limited to the specific geographical context of the Autonomous Provinces of Bolzano and Trento.

- **Relevance:**

    - The findings are significant for hydrological modeling and climate risk assessment, particularly in regions with limited observational data.
    - The research underscores the importance of accurate bias correction methods in improving the reliability of climate data for water resource management and planning under climate change.
 
## Comparison of Approaches

| Methodology/Technique              | Key Strengths                                                                                             | Key Limitations                                                                                   | Example Papers      |
|------------------------------------|-----------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|---------------------|
| **Artificial Neural Network (ANN)** | Remarkable flexibility and versatility, accommodating a wide range of data types. Capture complex data relationships and adjust to intricate patterns. | Demand significant computational resources and substantial training data.                         | Tanimu et al., 2024 |
| **Random Forest (RF)**             | Manage complex and nonlinear data relationships. Exceptional ability to capture nonlinear connections in climate data. | Can be sensitive to the quality of the input data.                                                 | Tanimu et al., 2024 |
| **Support Vector Machine (SVM)**   | Resilient to outliers and effective for nonlinear data using kernels. Performs well with high-dimensional data, even with limited samples. Effective in climate downscaling. | Computationally intensive for large datasets. Sensitive to hyperparameter selection. Limited interpretability, especially with complex kernels. | Tanimu et al., 2024 |
