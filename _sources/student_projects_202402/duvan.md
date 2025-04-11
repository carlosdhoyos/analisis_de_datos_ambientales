# Machine Learning Applications in Tropical Cyclone Analysis Using Satellite Imagery: A Literature Review

## Introduction
The analysis and prediction of tropical cyclones (TCs) has experienced significant advancement through the integration of machine learning techniques with satellite imagery. This review examines ten seminal papers that represent the evolution and current state-of-the-art in this field, with particular focus on recent developments like TC-GEN and TC-PRIMED that demonstrate the potential of AI-driven approaches in tropical cyclone research.

## Paper Reviews

### Paper 1: [The Advanced Dvorak Technique: Continued Development of an Objective Scheme to Estimate Tropical Cyclone Intensity Using Geostationary Infrared Satellite Imagery](https://journals.ametsoc.org/view/journals/wefo/22/2/waf975_1.xml)

![ADT algorithm satellite image analysis methodology for tropical cyclone intensity estimation](https://journals.ametsoc.org/view/journals/wefo/22/2/images/i1520-0434-22-2-287-f02.jpg "Citation: Weather and Forecasting 22, 2; 10.1175/WAF975.1")


- **Authors:** Timothy L. Olander and Christopher S. Velden
- **Key Highlights:**
 - Development and implementation of a fully automated tropical cyclone intensity estimation system
 - Systematic evolution from manual to automated technique (ODT->AODT->ADT)
 - World's first operational automated system for TC intensity estimation
 - Real-time implementation across multiple forecast centers
 - Decade-long validation against aircraft reconnaissance 
 - Integration of objective methods with established meteorological principles

- **Data Used:**
 - Geostationary satellite infrared imagery from GOES, GMS and Meteosat
 - Aircraft reconnaissance database (1995-2005):

- **Methodology:**
 - Automated pattern recognition algorithms:
     * Spiral centering technique for center location
     * Ring-fitting method for structure analysis
     * Automatic scene type classification
 - Statistical regression for intensity estimation
 - Latitude-based bias corrections
 - Integration of original Dvorak technique rules

- **Key Results:**
 - Elimination of systematic bias present in manual estimates
 - RMSE of 12.53 hPa vs 9.86 hPa for operational estimates
 - Optimal performance in mature storm stages
 - 50% accuracy improvement over original ODT algorithm
 
- **Strengths:**
 - Complete automation of decades-proven manual technique
 - Objective and consistent estimates without human intervention
 - Global applicability across all cyclone basins
 - 24/7 real-time operational capability
 - Extensive validation against aircraft reconnaissance data
 - Flexible implementation across multiple computational platforms

- **Limitations:**
 - Reduced accuracy during formation and dissipation stages
 - Significant difficulties with weak tropical systems
 - Limited to infrared imagery use only
 - Resolution constraints for very small cyclone eyes
 - Inability to fully replicate human expertise
 - Dependence on established empirical relationships
 - Lack of direct wind measurements
 - Challenges in wind shear conditions

- **Relevance:**
 - Demonstrates viability of automating complex satellite image analysis
 - Provides methodological framework for future ML applications
 - Identifies specific areas for improvement through ML techniques
 - Demonstrates operational viability of automated systems

### Paper 2: [Tropical cyclone intensity estimation using a deep convolutional neural network](https://ieeexplore.ieee.org/document/8082557)
- **Authors:** Pradhan, R., Aygun, R. S., Maskey, M., Ramachandran, R., & Cecil, D. J. 
- **Key Highlights:**
  - First implementation of deep CNN for tropical cyclone intensity estimation
  - Achieves better accuracy than traditional methods (Dvorak and DAVT)
  - Eliminates need for extensive preprocessing and domain expertise
  - Provides automated feature extraction from satellite imagery
  - Generalizable across Atlantic and Pacific regions

- **Data Used:**
  - 98 tropical cyclones (68 Atlantic + 30 Pacific) from 1999-2014
  - 8,138 original IR satellite images
  - Expanded to 48,828 images through transformations
  - HURDAT2 data for labeling
  - Separate recon-only test dataset of 2,646 images
  - Images taken at 2-hour intervals

- **Methodology:**
  - Deep CNN architecture:
      * 5 convolutional layers
      * 3 fully connected layers
      * ReLU activation functions
      * Local response normalization
      * Max pooling layers
      * Dropout (p=0.5) for regularization
  - Training:
      * GPU GRID K520 4GB
      * 65 epochs (~8 hours)
      * Mini-batch system
      * Learning rate: α=0.001 with γ=0.1 decay

- **Key Results:**
  - Classification accuracy:
      * Top-1: 80.66%
      * Top-2: 95.47%
  - RMSE: 10.18kt (Atlantic/Pacific)
  - Recon-only test results:
      * Top-1: 76.91%
      * Top-2: 92.55%
      * RMSE: 11.36kt
  - Outperforms previous DAVT techniques (14.7kt RMSE)

- **Strengths:**
  - Automated feature extraction
  - No requirement for domain expertise
  - Minimal preprocessing needed
  - Fast processing time (<1 second per image)
  - Generalizable across different regions
  - Lower RMSE than traditional methods
  - Robust visualization of learned features

- **Limitations:**
  - Dataset quality issues (grid lines in images)
  - Limited dataset size
  - Hardware resource constraints
  - Hyperparameter optimization challenges
  - Black patches in some images
  - Imbalanced category distribution

- **Relevance:**
  - Demonstrates successful application of deep learning in tropical cyclone analysis
  - Provides automated, accurate intensity estimation
  - Reduces human dependency in analysis
  - Establishes framework for future ML applications
  - Validates CNN approach for feature extraction
  - Shows potential for operational implementation

### Paper 3: [Machine Learning in Tropical Cyclone Forecast Modeling: A Review](https://www.mdpi.com/2073-4433/11/7/676)

![An organization chart of cases involving machine learning in tropical cyclone forecasts. The abbreviations used in this figure are as follows: logistic regression (LR), decision tree (DT), random forest (RF), support vector machine (SVM), support vector regression (SVR), multi-layer perceptron (MLP), convolutional neural network (CNN), generative adversarial network (GAN), recurrent neural network (RNN), hybrid radial basis function network (HRBF), self-organizing map (SOM), principal component analysis (PCA), convolutional long short-term memory network (ConvLSTM)](https://www.mdpi.com/atmosphere/atmosphere-11-00676/article_deploy/html/images/atmosphere-11-00676-g002.png)

- **Authors:** Chen, R., Zhang, W., & Wang, X. 
- **Key Highlights:** 
 - Comprehensive review of ML applications in TC forecasting
 - Analysis of different ML approaches for genesis/track/intensity prediction
 - Evaluation of ML integration with numerical weather prediction models
 - Assessment of opportunities and challenges in TC forecasting using ML
 - Framework for selecting appropriate ML methods for TC analysis

- **Data Used:** 
 - Satellite imagery (infrared, microwave, multispectral)
 - Reanalysis datasets (NCEP/NCAR, GFS-FNL)
 - Best track records from meteorological centers
 - In-situ observations & aircraft reconnaissance
 - Numerical model outputs (ECMWF, GFS, UKMET)
 - Multi-source environmental data (wind, temperature, pressure)

- **Methodology:**
 - Genesis Forecasting: LR, DT, RF, AdaBoost, SVM, CNN (short-term); SVR, MLP, hybrid networks (seasonal)
 - Track Prediction: RNN, MLP, GAN, ConvLSTM (neural networks); DT (feature mining); DBN, FMM (similarity)
 - Intensity Estimation: CNN variants (image analysis); RNN, LSTM (time series); CNN-LSTM (hybrid)
 - Impact Prediction: SVR/MLP/LSSVM (wind); SVM/hybrid networks (rainfall); MLP/SVR/BPN-ANFIS (surge)

- **Key Results:**
 - Genesis Detection: >90% accuracy in precursor identification
 - Track Prediction: Average errors <100km
 - Intensity Estimation: RMSE ~8kt using CNN
 - Impact Forecasting: Accurate predictions up to 6 hours
 - Model Improvement: Enhanced parameterization schemes

- **Strengths:**
 - Comprehensive coverage of ML applications
 - Detailed analysis of multiple approaches
 - Clear evaluation of methods' effectiveness
 - Strong focus on practical applications
 - Successful integration of traditional and ML methods

- **Limitations:**
 - Limited long-term prediction capability
 - Model interpretability challenges
 - Data scarcity for extreme events
 - Lack of standardized evaluation metrics
 - Implementation complexity in operational settings

- **Relevance:** 
 - Validates ML effectiveness in TC analysis using satellite imagery
 - Provides comprehensive methodological frameworks
 - Identifies promising research directions
 - Shows practical implementation paths
 - Establishes foundation for ML-enhanced TC analysis
 - Demonstrates successful integration of ML with traditional methods

### Paper 4: [Using Deep Learning to Estimate Tropical Cyclone Intensity from Satellite Passive Microwave Imagery](https://journals.ametsoc.org/view/journals/mwre/147/6/mwr-d-18-0391.1.xml)

![Simplified diagram of the standard convolutional neural network architecture](https://journals.ametsoc.org/view/journals/mwre/147/6/full-mwr-d-18-0391.1-f2.jpg "Citation: Monthly Weather Review 147, 6; 10.1175/MWR-D-18-0391.1")

- **Authors:** Wimmers, A., Velden, C., & Cossuth, J. H.
- **Key Highlights:**
 - Introduction of DeepMicroNet CNN model for TC analysis
 - Novel probabilistic output approach for intensity estimation
 - First successful deep learning implementation with microwave imagery
 - Integration of 37 and 85-92 GHz bands
 - Competitive performance with operational methods

- **Data Used:**
 - MINT dataset (1987-2012)
 - Multiple satellite sources (DMSP SSM/I, SSMIS, TRMM TMI, Aqua AMSR-E)
 - 400km x 400km images at 5km resolution
 - Filtered TC data over water
 - >65% scan coverage requirement

- **Methodology:**
 - CNN architecture based on AlexNet design
 - 15 convolutional layers + 2 fully connected layers
 - Cross-entropy loss function training
 - Data augmentation techniques
 - Three model versions (37 GHz, 89 GHz, combined)

- **Key Results:**
 - RMSE of 14.3 kt vs global best track
 - RMSE of 10.6 kt vs aircraft reconnaissance
 - 89 GHz band proved more influential
 - 6-hour forecasting capability
 - RMSE of 9.6 kt with high-resolution data

- **Strengths:**
 - Robust to partial scan coverage
 - Resistant to center-fixing errors
 - Provides uncertainty estimates
 - No manual calibration required
 - Global applicability
 - Operational-level performance

- **Limitations:**
 - Limited Category 5 hurricane performance
 - Training data constraints
 - Model interpretability challenges
 - Limited temporal resolution
 - Performance degradation beyond 6 hours
 - Satellite coverage gaps

- **Relevance:**
 - Demonstrates deep learning viability for TC analysis
 - Provides operational system foundation
 - Enables automated TC intensity estimation
 - Shows potential for method integration
 - Advances satellite-based TC analysis

### Paper 5: [Deep Learning for Hurricane Track Forecasting from Aligned Spatio-temporal Climate Datasets](https://hal.science/hal-01905408/)
- **Authors:** Giffard-Roisin, S., Yang, M., Charpiat, G., Kégl, B., & Monteleoni, C.
- **Key Highlights:**
 - Implementation of a novel moving frame of reference CNN model
 - Development of a fusion network architecture combining wind fields, pressure data, and trajectory information
 - First deep learning approach for 24h hurricane track forecasting using multiple atmospheric levels
 - Integration of data from both hemispheres in a single model

- **Data Used:**
 - IBTrACS database: >3000 storm tracks since 1979
 - ERA-interim reanalysis data:
   - Wind fields (u,v)  
   - Geopotential height
   - 3 pressure levels (700/500/225 hPa)
 - 25x25 degree grid centered on storm locations
 - 6-hourly temporal resolution

- **Methodology:**
 - Three-stream neural network architecture:
     1. Wind CNN: Processing wind field data
     2. Pressure CNN: Processing pressure data 
     3. Past tracks + meta NN: Processing trajectory and metadata
 - Fusion network combining all three streams
 - Moving reference frame approach
 - Training split: 60% train / 20% validation / 20% test

- **Key Results:**
 - Mean 24h forecast errors:
     - Fusion network: 128.9 km
     - Wind CNN: 141.1 km 
     - Pressure CNN: 161.3 km
     - Past tracks NN: 184.8 km
 - Outperformed statistical BCD5 model
 - Competitive with OFCL until 2010

- **Strengths:**
 - Effective data fusion approach
 - Global applicability (both hemispheres)
 - Moving reference frame innovation
 - Complementary to existing forecasting methods

- **Limitations:**
 - Performance not superior to post-2010 OFCL forecasts
 - Limited to 24-hour forecasts
 - Requires substantial computational resources
 - Dependent on quality of reanalysis data

- **Relevance:**
 - Demonstrates viability of deep learning for hurricane forecasting
 - Establishes framework for multi-source data fusion
 - Provides complementary approach to current forecasting methods
 - Potential for integration with existing prediction systems

### Paper 6: [Tropical Cyclone Intensity Estimation Using Multi-Dimensional Convolutional Neural Networks from Geostationary Satellite Data](https://www.mdpi.com/2072-4292/12/1/108)

![Graphical Abstract](https://pub.mdpi-res.com/remotesensing/remotesensing-12-00108/article_deploy/html/images/remotesensing-12-00108-ag.png?1579088259 )

- **Authors:** Lee, J., Im, J., Cha, D. H., Park, H., & Sim, S.
- **Key Highlights:**
  - First implementation of multi-spectral analysis for TC intensity estimation using CNNs
  - Development of both 2D and 3D CNN architectures for TC analysis
  - Introduction of heat maps for model interpretation
  - Improvement of ~35% over existing single-channel methods

- **Data Used:**
  - COMS MI satellite data (2011-2016)
  - 4 infrared channels: SWIR (3.7μm), WV (6.7μm), IR1 (10.8μm), IR2 (12.0μm)
  - JTWC best track data for validation
  - Additional validation data from 2017 TCs

- **Methodology:**
  - Image preprocessing: 301x301 pixel patches resized to 101x101
  - Data balancing through subsampling and oversampling
  - 2D-CNN and 3D-CNN architectures implementation
  - Multiple evaluation metrics (MAE, RMSE, rRMSE, ME, MPE, NSE)

- **Key Results:**
  - 2D-CNN model: RMSE = 8.32 kts
  - 3D-CNN model: RMSE = 11.34 kts
  - 35% improvement over previous single-channel models
  - Successful validation on 2017 cases

- **Strengths:**
  - Multi-spectral analysis capability
  - Automated and objective estimation
  - Model interpretability through heat maps
  - Consistent with Dvorak technique patterns

- **Limitations:**
  - High computational demands for 3D-CNN
  - Limited hyper-parameter optimization
  - Difficulty in fully understanding model decisions
  - Computational resource constraints

- **Relevance:**
  - Provides automated TC intensity estimation
  - Improves accuracy over traditional methods
  - Offers real-time analysis potential
  - Contributes to operational meteorology

### Paper 7: [Physics-Augmented Deep Learning to Improve Tropical Cyclone Intensity and Size Estimation from Satellite Imagery](https://journals.ametsoc.org/view/journals/mwre/149/7/MWR-D-20-0333.1.xml)

![The configuration of DeepTCNet in both single-task and multitask learning frameworks.](https://journals.ametsoc.org/view/journals/mwre/149/7/full-MWR-D-20-0333.1-f1.jpg "Citation: Monthly Weather Review 149, 7; 10.1175/MWR-D-20-0333.1")

- **Authors:** Zhuo, J. Y., & Tan, Z. M.
- **Key Highlights:**
  - Development of DeepTCNet: A physics-augmented deep learning framework for TC analysis
  - Novel integration of physical knowledge into CNN architecture
  - First comprehensive DL approach for simultaneous TC intensity and wind radii estimation
  - Significant improvement over traditional methods (ADT and MTCSWA)

- **Data Used:**
  - IBTrACS database (2005-2019) for intensity and wind radii
  - HURSAT-B1 IR imagery (up to 2016)
  - GridSat-B1 archive (post-2016)
  - TC Vitals Database for auxiliary storm information
  - Training: 2005-2015
  - Validation: 2016, 2018
  - Testing: 2017, 2019

- **Methodology:**
  - Base Architecture: Modified VGGNet with 13 layers
  - Single-Task Learning (STL) for intensity estimation
  - Multi-Task Learning (MTL) for wind radii estimation
  - Physics augmentation through:
      - TC fullness integration
      - Auxiliary physical information
      - Sequential IR imagery analysis

- **Key Results:**
  - 39% improvement over ADT in intensity estimation
  - 32% improvement over MTCSWA in wind radii estimation
  - Comparable performance to SATCON
  - Relative error ~8% for all TC categories
  - Successful validation with aircraft reconnaissance data

- **Strengths:**
  - Real-time operational capability
  - Interpretable through saliency maps and LRP
  - Effective physics integration
  - Simultaneous multi-parameter estimation
  - Basin-independent application potential

- **Limitations:**
  - Underestimation of very intense TCs
  - Limited training data for extreme events
  - Dependent on IR imagery resolution
  - Requires quality-controlled historical data
  - Performance varies with TC structure complexity

- **Relevance:**
  - Advances operational TC monitoring capabilities
  - Improves satellite data utilization efficiency
  - Demonstrates successful physics-ML integration
  - Provides foundation for future TC analysis systems
  - Supports real-time decision making

### Paper 8: [DMANet_KF: Tropical Cyclone Intensity Estimation Based on Deep Learning and Kalman Filter From Multispectral Infrared Images](https://ieeexplore.ieee.org/document/10121612)

![Flowchart of the proposed method](https://ieeexplore.ieee.org/mediastore/IEEE/content/media/4609443/9973430/10121612/jiang1-3273232-large.gif )

- **Authors:** Jiang, W., Hu, G., Wu, T., Liu, L., Kim, B., Xiao, Y., & Duan, Z.
- Key Highlights:
  - Introduction of DMANet (Deep Multisource Attention Network)
  - Novel Message-Passing Enhancement Module (MPEM)
  - Local Global Attention Module (LGAM)
  - First-time application of Kalman Filter for TC intensity correction

- **Data Used**:
  - Japanese Meteorological Satellites data (MTSAT-1R, MTSAT-2, HIMAWARI-8)
  - Period: 2007-2021
  - 343 Tropical Cyclones
  - Four infrared channels (IR1: 10.3-11.3 μm, IR2: 11.5-12.5 μm, IR3: 6.5-7.0 μm, IR4: 3.5-4.0 μm)

- **Methodology**:
  - DMANet architecture with MPEM and LGAM modules
  - MPEM based on conditional random fields (CRFs)
  - LGAM with local and global attention mechanisms
  - Kalman Filter for time series correction
  - Data preprocessing including image transformation and resampling

- **Key Results**:
  - RMSE reduction from 9.79 to 7.82 knots with Kalman Filter
  - 9.07% improvement over existing methods
  - Best performance in violent category TCs
  - Outperforms general models (AlexNet, VGG-16, ResNet-50)

- **Strengths**:
  - Effective multispectral data integration
  - Automatic feature extraction
  - Real-time processing capability
  - Robust performance across TC categories
  - Innovative time series correction

- **Limitations**:
  - Dataset imbalance issues
  - Limited to Northwest Pacific Basin
  - Dependent on clear satellite imagery
  - Computational resource requirements
  - Regional specificity

- **Relevance**:
  - Advances in TC intensity estimation
  - Improved disaster preparedness
  - Automated analysis system
  - Enhanced accuracy in violent TC category
  - Integration of multiple data sources

## Comparison of Approaches
| Methodology/Technique          | Key Strengths                                                                 | Key Limitations                                                  |
|--------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------|
| Traditional Automated Methods (ADT) | - Complete automation of proven manual techniques<br>- Global applicability<br>- 24/7 operational capability<br>- Extensive validation | - Reduced accuracy during formation/dissipation<br>- Limited to infrared imagery<br>- Resolution constraints<br>- Cannot fully replicate human expertise |
| Deep CNN                       | - Automated feature extraction<br>- Minimal preprocessing needed<br>- Fast processing time<br>- Generalizable across regions<br>- Better accuracy than traditional methods | - Dataset quality issues<br>- Limited dataset size<br>- Hardware resource constraints<br>- Hyperparameter optimization challenges |
| Multi-spectral CNN             | - Multi-channel analysis capability<br>- Improved accuracy over single-channel<br>- Model interpretability via heat maps<br>- Consistent with traditional patterns | - High computational demands<br>- Limited hyperparameter optimization<br>- Model interpretability challenges<br>- Resource constraints |
| Physics-Augmented Deep Learning| - Real-time operational capability<br>- Interpretable results<br>- Effective physics integration<br>- Simultaneous multi-parameter estimation | - Underestimation of intense TCs<br>- Limited extreme event data<br>- IR imagery resolution dependency<br>- Variable performance with TC structure |
| Deep Multisource Attention Network | - Effective multispectral integration<br>- Automatic feature extraction<br>- Real-time processing<br>- Robust cross-category performance | - Dataset imbalance issues<br>- Regional specificity<br>- Clear imagery dependency<br>- High computational requirements |


## Challenges and Future Directions
### Data-Related Challenges
- Limited availability of high-quality labeled data  
- Imbalanced datasets across TC categories  
- Inconsistent data quality across different satellite sources  
- Gaps in temporal coverage  

### Technical Challenges
- High computational resource requirements  
- Model interpretability issues  
- Integration of physical constraints with ML models  
- Real-time processing limitations  

### Future Research Directions
- Development of hybrid models combining physical and ML approaches  
- Improved techniques for handling data imbalance  
- Enhanced model interpretability methods  
- Cross-basin generalization techniques  
- Integration of multiple data sources  
- Advanced time series analysis methods  
- Real-time processing optimization  

## Conclusion
The review of these papers reveals significant progress in applying machine learning to tropical cyclone analysis, particularly in the areas of intensity estimation and track prediction. Key developments include:  
- Evolution from traditional automated methods to sophisticated deep learning approaches  
- Successful integration of physical understanding with ML techniques  
- Improved accuracy through multi-spectral analysis  
- Development of real-time operational capabilities  

The field is moving toward more sophisticated hybrid approaches that combine the strengths of traditional methods with modern ML techniques. The most promising directions appear to be in physics-augmented deep learning and multi-source data integration approaches.

## Questions About Methodologies and ML Approaches
### Data Preparation and Quality
- How are satellite imagery inconsistencies handled across different sources?  
- What preprocessing steps are critical for model performance?  
- How is data augmentation implemented effectively?  

### Model Architecture
- What factors determine the optimal network depth and complexity?  
- How are physical constraints incorporated into neural network architectures?  
- What attention mechanisms are most effective for TC analysis?  

### Training Process
- How are hyperparameters optimized across different approaches?  
- What strategies address class imbalance issues?  
- How is overfitting prevented with limited data?  

### Evaluation Metrics
- What metrics best capture real-world operational requirements?  
- How is model performance compared across different basins?  
- What validation approaches ensure operational reliability?  

### Practical Implementation
- How are models deployed in operational settings?  
- What computational resources are required for real-time analysis?  
- How is model maintenance and updating handled?  

### Reproducibility
- What details are needed to reproduce results?  
- How are model weights and architectures shared?  
- What benchmarking procedures ensure consistent evaluation?  

## References

1. Olander, T. L., & Velden, C. S. (2007). The advanced Dvorak technique: Continued development of an objective scheme to estimate tropical cyclone intensity using satellite infrared imagery. *Weather and Forecasting*, 22(2), 287-298. https://doi.org/10.1175/WAF975.1
2. Pradhan, R., Aygun, R. S., Maskey, M., Ramachandran, R., & Cecil, D. J. (2017). Tropical cyclone intensity estimation using a deep convolutional neural network. *IEEE Transactions on Image Processing*, 27(2), 692-702. https://doi.org/10.1109/TIP.2017.2766358
3. Chen, R., Zhang, W., & Wang, X. (2020). Machine learning in tropical cyclone forecast modeling: A review. *Atmosphere*, 10(9), 496. https://doi.org/10.3390/atmos11070676
4. Wimmers, A., Velden, C., & Cossuth, J. H. (2019). Using deep learning to estimate tropical cyclone intensity from satellite passive microwave imagery. *Monthly Weather Review*, 147(6), 2261-2282. https://doi.org/10.1175/MWR-D-18-0391.1
5. Giffard-Roisin, S., Yang, M., Charpiat, G., Kégl, B., & Monteleoni, C. (2018, December). Deep learning for hurricane track forecasting from aligned spatio-temporal climate datasets. In Modeling and decision-making in the spatiotemporal domain NIPS workhop. https://hal.science/hal-01905408v1 
6. Lee, J., Im, J., Cha, D. H., Park, H., & Sim, S. (2019). Tropical cyclone intensity estimation using multi-dimensional convolutional neural networks from geostationary satellite data. Remote Sensing, 12(1), 108. https://doi.org/10.3390/rs12010108 
7. Zhuo, J. Y., & Tan, Z. M. (2021). Physics-augmented deep learning to improve tropical cyclone intensity and size estimation from satellite imagery. Monthly Weather Review, 149(7), 2097-2113. https://doi.org/10.1175/MWR-D-20-0333.1 
8. Jiang, W., Hu, G., Wu, T., Liu, L., Kim, B., Xiao, Y., & Duan, Z. (2023). DMANet_KF: Tropical cyclone intensity estimation based on deep learning and Kalman filter from multispectral infrared images. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing, 16, 4469-4483. https://doi.org/10.1109/JSTARS.2023.3273232
