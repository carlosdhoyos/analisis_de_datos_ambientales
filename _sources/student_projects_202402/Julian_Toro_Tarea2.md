
# Machine learning for intraseasonal variability detection or prediction (still to be define): A Literature Review

## Introduction

Intraseasonal variability (ISV) represents one of the most significant sources of climate variability, 
occurring on timescales ranging from 30 to 90 days, 
and profoundly influencing global weather patterns and regional extreme events. 
The Madden-Julian Oscillation (MJO) is one of the most prominent examples of ISV, 
driving planetary-scale interactions between tropical convection and atmospheric circulation. 
Traditional methods, such as statistical and dynamical models, 
have made significant progress in understanding and uncovering some of the mechanisms behind intraseasonal variability. 
However, recent advances in machine learning and artificial intelligence offer a novel approach to enhance the identification and prediction of intraseasonal phenomena like the MJO. These new algorithms and computational frameworks show promising results, achieving comparable or better performance with significantly reduced computational demands compared to traditional dynamical models.

In this review, we explore machine learning techniques for teleconnection detection, starting with the use of self-organizing maps to identify the influence of the Madden-Julian Oscillation (MJO) on regions in Africa. The second approach highlights the Sequential Autoencoder for Teleconnection Analysis (SATA), a method designed to detect and extract intraseasonal variability (ISV) patterns. Lastly, we examine a deep learning filter based on convolutional neural networks, which is used to isolate ISV signals effectively.

Additionally, we review methodologies for predicting future states of the MJO using artificial neural networks, convolutional neural networks, and probabilistic techniques. These approaches demonstrate promising results when compared to traditional dynamical models, offering improved efficiency and comparable predictive skill with less computational demand.

## Paper Reviews

### Paper 1: The self-organizing map, a new approach to apprehend the Madden–Julian oscillation influence on the intraseasonal variability of rainfall in the southern African region.
- **Authors:** Pascal Oettli, Tomoki tozuka, Takeshi Izumo Francois A. Engelbrecht and Toshio Yamagata

- **Key Highlights:** 
Looks to reduce high-dimensionality data st into a low dimensional version.
SOM is not constrained by orthogonality and linearity, and for the applications
described here, only bandpass ﬁltered OLRanomalies are needed, compared to ﬁltered OLR and zonal wind anomalies 

- **Data Used:** The 5-day version of the CPC merged analysis of precipitation
(CMAP) dataset . 
The outgoing longwave radiation (OLR) MJO NOAA. 
The NOAA High-resolution Blended Analysis of Daily
Sea Surface Temperature (SST) and Ice dataset 
- **Methodology:** Use Self organizin map: Classification is based on an unsupervised artificial neural network.
Input: 2,190 vectors, made up of pentads of bandpass ﬁltered OLR for the period 1980–2009
Output: Reference Vectors.
Method requirers training.
- **Key Results:** conﬁrmed the existence of a 10-day lag between
the tropical forcing over the Indian Ocean and the response
in both convection and rainfall in the SAR. 
demonstrated the apparent importance of the region 65E–85E/10S–
10N for the rainfall in the SAR. 

- **Strengths:** The SOM is not constrained
by orthogonality and linearity
- **Limitations:** SOM applied on unﬁltered OLR
anomalies tends to include non-MJO features inside MJO
nodes, because of similar OLR pattern
- **Relevance:** This method of Self organizing maps show capture patterns of MJO teleconnections. Article shows that SOM can distinguish patterns with weak and strong signals in convection.

### Paper 2: A Sequential Autoencoder for Teleconnection Analysis

- **Authors:** Jiena He, J. Ronald Eastman

- **Key Highlights:** 
introduces a novel, efficient method to extract teleconnection patterns by iteratively isolating spatial-temporal modes through residual analysis.
Faster than traditional methods like empirical orthogonal teleconnections (EOT) and principal component analysis (PCA).
SATA handles teleconnections with multiple centers of action.
The method is transparent and reproducible.

- **Data Used:** Interpolated monthly sea surface temperature imagery at a 1 degree
resolution
Resolution: 1° spatial resolution, processed as anomalies standardized over time
Projection: Mollweide projection ensures equal area weighting across pixels
- **Methodology:** Uses Autoencoder with hidden layers.
Input: Time series of images and weights
Output: an image which is a function of the
decoder weights and the scalar value of the hidden node vector at each time step
- **Key Results:**  Correlation with Climate Indices: SATA components achieved higher correlations with established teleconnection indices (e.g., Oceanic Niño Index, Atlantic Multidecadal Oscillation) compared to EOT.
New Teleconnections: SATA identified patterns such as the Antarctic Dipole (ADI) and South Atlantic Ocean Dipole (SAOD), not detected by EOT in the first 10 components.
Efficiency in Pattern Extraction: SATA captures deep residuals, such as the Pacific Meridional Mode (PMM), even at the 9th or 10th component.
- **Strengths:** The SATA method is significantly faster than empirical orthogonal teleconnections (EOT) and principal components analysis (PCA), achieving results in orders of magnitude less time.
Improved Pattern Detection: SATA identifies teleconnection patterns with stronger correlations to known climate indices and can effectively handle multiple centers of action.
Dimensionality Reduction: Uses a linear autoencoder to reduce the data dimensionality while retaining meaningful temporal-spatial patterns.
Reproducibility: The methodology and code are openly available, ensuring transparency and usability.
- **Limitations:** SATA relies heavily on correlation for identifying key patterns. This focus could make it sensitive to noise or non-linear relationships that might exist but are not captured by simple linear correlation.

- **Relevance:** Enhancing Climate Pattern Understanding: By extracting clearer and more accurate teleconnection patterns, it aids in understanding global climate dynamics
SATA is suitable for analyzing large, complex datasets common in climate and remote sensing studies, making it a valuable tool for researchers.
The speed and simplicity of the method make it accessible for broader use, including real-time climate monitoring and modeling.

### Paper 3: A Deep Learning Filter for the Intraseasonal Variability of the Tropics

- **Authors:** Cristiana Stan, Rama Sesha Sridhar Mantripragada
- **Key Highlights:** 
High Agreement with Conventional Filters:
Index of Agreement (IOA) of 95–99% with Lanczos-filtered results.
Retains variability within the 30–90-day range with minimal spurious frequencies.
Accurately extracts MJO signals, outperforming proxy methods, and improves phase and amplitude consistency.
- **Data Used:** 
Wind stress: Blended Sea Winds (1988–2016) and Advanced Scatterometer.
Daily means of NOAA interpolated OLR 
- **Methodology:**
Two convolutional layers with kernel sizes 90 and 30 days.
Extracts intraseasonal variability progressively by filtering variability above 90 days and isolating 30–90-day variability.
input: Time series and weights
- **Key Results:**   
Accurately extracts MJO signals, outperforming proxy methods, and improves phase and amplitude consistency.
Low mean error and standard deviation, especially beyond the start of the testing period.
Retains variability within the 30–90-day range with minimal spurious frequencies.
- **Strengths:**  
Introduces a CNN-based filter that efficiently extracts intraseasonal variability (ISV) signals in the 30–90-day range.
Versatile application to different atmospheric fields, including zonal wind stress and outgoing longwave radiation (OLR).
Outperforms conventional filters (e.g., Lanczos) on shorter time series, which are common in operational forecasting.
Produces physically interpretable outputs, maintaining coherence with known patterns like the Madden-Julian Oscillation (MJO).
- **Limitations:** 
requires adequate training data to achieve high accuracy
small reduction in accuracy at the beginning and end of the time series
The CNN filter is constrained by the kernel sizes used
overfitting remains a common concern in deep learning approaches.
does not consider spatial pattern information

- **Relevance:** 
Better suited for real-time monitoring of tropical intraseason variability signals.
Supports analysis of tropical-extratropical teleconnections and MJO-related weather phenomena.
Could be adapted for even shorter S2S forecasts, further enhancing operational prediction systems.

### Paper 4: Using Simple, Explainable Neural Networks to Predict the Madden-Julian Oscillation

- **Authors:** Zane K.Martin, Elizabeth A. Barnes and Eric Maloney
- **Key Highlights:** 
ANNs outperform traditional statistical models.
Provides Computationally affordable alternative to complex dynamical models.
- **Data Used:** 
Real time multivariate MJO index.
Zonal winds at 850hPa and 200 hPa
OLR data from NOAA
NOAA OI SST V2 High Resolution data set 
ERA data at 2.5 X 2.5 
- **Methodology:**
Artificial Neural Networks one regression model and a classification model.
Regression ANN: Predicts MJO indices (RMM1 and RMM2) at specific lead times.
Classification ANN: Outputs the probability of the MJO being active in a specific phase.
Inputs: OLR, zonal winds at 850hPa and 200hPa. Processed daily maps.
output: Models returns information about the RMM index in the future.
- **Key Results:**   
Winter: Predicts MJO skillfully for ~18 days using regression models and ~16 days probabilistically.
Summer: Predicts MJO for ~11 days, with better performance than traditional statistical models.
ANNs outperformed persistence, vector autoregressive (VAR), and multi-linear regression (MLR) models, especially at longer lead times.
- **Strengths:**  
Simplicity and Efficiency: Implements shallow artificial neural networks (ANNs) that are computationally inexpensive compared to dynamical models.
Utilizes explainable AI (XAI) techniques like layer-wise relevance propagation (LRP) to identify the key regions and variables influencing prediction skill.
 Demonstrates that simple machine learning (ML) models can achieve results comparable to more complex frameworks, encouraging adoption in the climate community.
- **Limitations:** 
achieve prediction skill up to ~18 days in winter and ~11 days in summer,
which is significantly shorter than the ~25–35 days typical of state-of-the-art dynamical models.
architectures struggle to accurately predict weak MJO events.
cannot directly capture MJO strength or location as precisely as regression models.
- **Relevance:** 
 Demonstrates the potential of ML for improving subseasonal-to-seasonal (S2S) MJO predictions.
 The framework can be applied to study other Earth system phenomena beyond the MJO.
 ### Paper 5: Machine learning prediction of the Madden-Julian oscillation

- **Authors:** Riccardo Silini, Marcelo Barreiro and Cristina Masoller.
- **Key Highlights:** 
 found a prediction skill of 26–27 days, which is comparable to most dynamical
models.
 major advantage of the ANNs considered is that they are
computationally low-cost
- **Data Used:** 
Real time multivariate MJO index.
Zonal winds at 850hPa and 200 hPa
OLR data from NOAA
- **Methodology:**
Artificial Neural Networks 
Feed forward Neural network
Autoregressive recurrent neural network.

- **Key Results:**   
Acceptable prediction of the RMM phase compare to dynamical models
large variability in prediction skills in boreal winter and fall
most difficult conditions to predict MJO is in boreal fall
when the initial MJO phase is phase 1
- **Strengths:**  
Implements artificial neural networks (ANNs) that are computationally inexpensive compared to dynamical models.
the very own nature of ANNs preclude the understanding of the physical processes involved and thus they represent a complementary approach with dynamical models 
- **Limitations:** 
ANN prediction skill is not comparable to dynamical models
poor prediction of the RMM amplitude, which was systematically underestimated.
- **Relevance:** 
Use of low computational cost methods to generate relevant predictions in the phase and amplitude of the MJO. Where the phase prediction showed well behaviour.

 ### Paper 6: Interpretable Deep Learning for Probabilistic MJO Prediction

- **Authors:** Antoine Delaunay and  Hannah M. Christensen

- **Key Highlights:** 
 CNN spreads are correlated with actual forecast errors, unlike many dynamical models.
 CNNs complement dynamical models, with potential for hybrid approaches to further improve MJO forecasting.
- **Data Used:** 
Daily anomalies of outgoing longwave radiation (OLR), 
zonal wind (850 hPa and 200 hPa), 
specific humidity (400 hPa), 
and sea surface temperature (SST).
- **Methodology:**
Convolutional neural network.
Input: Maps of six atmospheric variables over the tropics.
Outputs: Predicted means and variances of real-time multivariate MJO (RMM) indices (RMM1 and RMM2).
- **Key Results:**   
probabilistic forecasts outperform traditional models in reliability and calibration, especially for short lead times.
Stronger initial MJO signals correspond to higher forecast uncertainty, linked to variability in the Walker Circulation.
- **Strengths:**  
The convolutional neural network (CNN) dynamically adjusts forecast uncertainty based on the predictability of the Madden-Julian Oscillation (MJO) under given conditions.
 The CNN is as skillful as state of the art dynamical models from the Subseasonal-to-Seasonal (S2S) database, with superior probabilistic reliability at short lead times (1–5 days).
- **Limitations:** 
The CNNs uncertainty estimates might be less reliable during rare or extreme MJO events, as such conditions are underrepresented in the training data.
The study emphasizes 10-day forecasts, and the conclusions regarding predictability might differ for longer lead times, where different features and uncertainties could dominate.
- **Relevance:** 
The framework can be extended to other climate phenomena, improving Earth system predictability.
The models ability to adjust uncertainty dynamically provides actionable insights for probabilistic MJO forecasts.

## Comparison of Approaches
| Methodology/Technique | Key Strengths                   | Key Limitations                   | Example Papers                  |
|------------------------|---------------------------------|-----------------------------------|---------------------------------|
| Self organizing map |  is not constrained by orthogonality and linearity    | applied on unﬁltered OLR anomalies tends to include non-MJO features inside MJO nodes    | Oettli et al.(2013)        |
| Autoencoder with hidden layers | identifies teleconnection patterns with stronger correlations to known climate indices| relies heavily on correlation for identifying key patterns | He et al.(2020)  |
| Two convolutional layers | efficiently extracts intraseasonal variability (ISV) signals in the 30–90-day range | filter is constrained by the kernel sizes |  Stan et al.(2023)|
| Artificial Neural Networks| computationally inexpensive compared to dynamical models  | Has limitations for long-range forecasts (25-35 días) | Martin et al.(2022)|
|Artificial Neural Networks|complementary approach with dynamical models|poor prediction of the RMM amplitude|Silini et al.(2021)|
|Convolutional neural network|probabilistic reliability at short lead times (1–5 days)| estimates might be less reliable during rare or extreme MJO events|Delaunay et al.(2021)|

## Challenges and Future Directions
- Use of simple ANN can be used not only for predictions but for hypothesis testing.
- Use of filters like the CNN in the extraction of signals from S2S forecast models which are shorter than 45 days.
- Improvement in code availability for replication of models.
- Usage of Machine learning techniques that are more robust in capturing signals that EOT analysis.
- Use of deep learning and Neural networks for the detection of signals in different time scales.
- MJO prediction skill could be potentially improved by training the ANNs independently for each season.
- Use of Artificial neural network alongside dynamical models could improve forecast.
## Conclusion

With the rise of new algorithms and techniques based on artificial intelligence and machine learning, we are witnessing more robust and precise methods to detect and extract patterns that were previously challenging for traditional decomposition approaches. In this review, we examined various machine learning techniques for identifying and extracting teleconnection patterns on intraseasonal timescales. For instance, the use of convolutional neural networks (CNNs), as demonstrated by Stan et al. (2023), has shown notable improvements in representing Madden-Julian Oscillation (MJO) signals by retaining signal coherence.

Moreover, the application of CNNs and artificial neural networks (ANNs) has yielded promising results in forecasting the MJO over short periods. The key advantage of these models lies in their low computational requirements compared to traditional dynamical models. However, these methods still require further refinement, as their accuracy does not yet match that of dynamical models. Some studies have suggested that combining machine learning approaches with traditional dynamical models could lead to more robust and reliable results.

The approaches presented in this review, both for signal detection and MJO prediction, are particularly relevant to this semester's research. In the case of teleconnections, the use of convolutional neural networks appears to be a compelling avenue to explore, as it aligns with current research efforts, offers general applicability, and can be readily replicated. On the other hand, the work of Martin et al. (2022) provides an excellent starting point for utilizing ANNs in forecasting, making it a promising tool for further investigation.

## Questions About Methodologies and ML Approaches
This section identifies critical questions that guide understanding of the methodologies and machine learning (ML) techniques used in the reviewed papers. It covers aspects such as data preparation, model design, training processes, evaluation metrics, reproducibility, and practical applications. The purpose is to highlight areas where additional clarity or details are needed to replicate or extend the research, especially for those less familiar with the technical intricacies.

1. Why we use band filtered data for some methodologies?
3. What is the Kernel and what process performs for the ANN or CNN?
4. Differences between Artificial neural networks and Convolutional Neural Networks?
5. How do we evaluate model performance?
6. Are there different loss functions and how do they work?
7. How do you determine which neural network architecture to use?
8. In which cases does the data require preprocessing?
9. What kind of computational power does it takes to run this models? 
10. How can one determine if the extracted signals are relevant?
11. Are the models sensitive to grid size?


## References
1. Oettli, P., Tozuka, T., Izumo, T., Engelbrecht, F. A., & Yamagata, T. (2014). The self-organizing map, a new approach to apprehend the Madden–Julian oscillation influence on the intraseasonal variability of rainfall in the southern African region. Climate dynamics, 43, 1557-1573.
2. Martin, Z. K., Barnes, E. A., & Maloney, E. (2022). Using simple, explainable neural networks to predict the Madden‐Julian oscillation. Journal of Advances in Modeling Earth Systems, 14(5), e2021MS002774.
3. Stan, C., & Mantripragada, R. S. S. (2023). A deep learning filter for the intraseasonal variability of the tropics. Artificial Intelligence for the Earth Systems, 2(4), e220079.
4. He, J., & Eastman, J. R. (2020). A sequential autoencoder for teleconnection analysis. Remote Sensing, 12(5), 851.
5. Delaunay, A., & Christensen, H. M. (2022). Interpretable deep learning for probabilistic MJO prediction. Geophysical Research Letters, 49(16), e2022GL098566.
6. Silini, R., Barreiro, M., & Masoller, C. (2021). Machine learning prediction of the Madden-Julian oscillation. npj Climate and Atmospheric Science, 4(1), 57.