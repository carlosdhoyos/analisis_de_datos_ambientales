# Precipitation Nowcasting: A Literature Review

## Introduction

Precipitation nowcasting consists of predicting the movement and evolution of the precipitation field with a time horizon of up to 120 minutes. This approach is characterized by its high spatial (~1 km) and temporal (~5-10 minutes) resolution, which makes it an essential tool for mitigating disasters associated with heavy rainfall events, such as floods and landslides. In addition, nowcasting provides information tools for industries such as agriculture and transportation, so its proper implementation will not only contribute to improving risk management and decision-making, but will also strengthen the climate resilience of the region, benefiting both the population and the productive sectors.

However, achieving effective temporal-spatial resolution nowcasting is a very challenging task owing to the complex dynamics and chaos. Recently, an increasing amount of research has focused on utilizing deep learning approaches for this task because of their powerful abilities in learning spatiotemporal feature representation in an end-to-end manner.

## Paper Reviews

### Paper 1: Skillful precipitation nowcasting using deep generative models of radar
- **Authors:** Ravuri et al. (2021)
- **Key Highlights:** 
   - The model produces realistic spatiotemporal predictions over regions up to 1,536 km x 1,280 and with lead times from 5-90 min ahead.
   - Skillful nowcasting without resorting to blurring.
   - Deep Generative Nowcasting (DGN) can provide probabilistic predictions that improve forecast value and support operational utility.
- **Data Used:** 
    - Radar observations of UK dataset from 2016 to 2018 for training and 2019 for testing.
    - Includes orographic enhancement and mean field adjustment using rain gauges.
- **Methodology:**
    - **Model Architecture:** Conditional Generative Adversarial Network (GAN) using radar-based surface precipitation integrated with latent random variables.
    - **Inputs and Outputs:** Four consecutive radar observations (previous 20 min) are used as context for a generator that allows sampling of multiple 90 min reliazations.
    - **Loss functions:** Learning is driven by two loss functions and a regularization term:
        - Spatial discriminator: CNN that aims to distinguish observed radar fields from generated fields. Ensure spatial consistency and discourage blurriness.
        - Temporal discriminator: 3D CNN that aims to distinguish observed and generated radar sequences. Imposes temporal consistency and penalizes jumpy predictions.
    - **Evaluation metrics:** Compared against baseline methods with critical success index (CSI), radially averaged power spectral density (PSD) and continuos ranked probability score (CRPS).
- **Key Results:**
    - DGMR outperforms pySTEPS, UNet, and MetNet.
    - Medium- and small-scale precipitation variability in Axial attention (MetNet) and UNet forecasts decreases with increasing lead time (they produce blurred predictions).
    - DGMR provides greater decision-making value when assessed using both economic and cognitive analyses.
- **Strengths:**
    - Introduce a regularization term that penalizes deviations at the grid cell resolution between real radar sequences and the model predictive mean to produce location-accurate predictions and improve performance.
    - Probabilistic forecasts that are more location accurate and preserve the statistical properties of precipitation across spatial and temporal scales without blurring.
    - Improved forecast quality, consistency and value, providing fast and accurate short-term predictions at lead times where other methods struggle.
- **Limitations:**
    - Comparison with other methods is applied only to one single case.
    - Prediction of heavy precipitation at long lead times remains difficult for this approach.
- **Relevance:**
    - Highlights the potential of deep generative models for precipitation nowcasting.
    - Demonstrates the importance of better verification methods.

### Paper 2: Deep Learning for Precipitation Nowcasting: A Benchmark and A New Model
- **Authors:** Shi et al. (2017)
- **Key Highlights:** 
    - Introduce Trajectory Gated Recurrent Unit (TrajGRU) model that can actively learn the location-variant structure for recurrent connections.
    - Provides a benchmark that includes a real-world, large-scale dataset from HKO, a new training loss, and a comprehensive evaluation protocol to facilitate future research.
- **Data Used:** Rain rate level converted from radar 2 km altitude CAPPI reflectivity with resolution of 480 x 480 pixels taken every 6 minutes using Z-R relationship.
- **Methodology:**
    - **Model Architecture:** Trajectory Gated Unit, which has the ability of learning the recurrent connection structure.
    - **Inputs and Outputs:** 
        - 812 days for training, 50 days for validation and 131 days for testing.
        - Two settings for evaluation:
            - Offline: Receives 5 frames as input and predicts 20 frames ahead.
            - Online: Receives segments of 5 lengths sequentially and predicts 20 frames ahead for each new segment received.
    - **Loss functions:** As different rainfall levels are highly imbalanced. They propose to use B-MSE and B-MAE, which are weighted loss functions to help solve this problem.
    - **Models for comparison:** Compared against two optical flow methods (ROVER and its nonlinear version) and four deep learning methods (ConvGRU, as well as 2D and 3D CNNs).
    - **Evaluation metrics:**  Critical success index (CSI) and Heidke Skill Score for multiple precipitation thresholds.
- **Key Results:**
    - TranjGRU outperforms other methods in MovingMNIST++ and HKO datasets.
    - All deep learning models outperform the optical flow based models.
    - Performance with online fine-tuning enabled is consistently better than that without online fine-tuning.
    - For the benchmark, the HKO-7 dataset, which contains radar echo data from 2009 to 2015 near Hong Kong was built.
- **Strengths:**
    - Propose B-MSE and B-MAE for training and evaluation, which assign more weights to heavier rainfalls in the calculation of MSE and MAE. Balanced variants of loss functions are more consistent with overall nowcasting performance at multiple rain rate thresholds than original loss functions.
- **Limitations:**
    - Nowcasting is treated as a video task and does not include information for new convection prediction.
- **Relevance:**
    - Highlights the importance of balance loss functions to get better predictions of heavy precipitation events.
    - Describes processing of radar files and emphasizes the importance of online fine-tuning.


### Paper 3: PreDiff: Precipitation Nowcasting with Latent Diffusion Models
- **Authors:** Gao et al. (2023)
- **Key Highlights:**
    - Develop PreDiff, a conditional latent diffusion model (LDM) capable of probabilistic forecasts.
    - Incorporate an explicit knowledge alignment mechanism to align forecasts with domain-specific physical constraints.
- **Data Used:**
    - Two datasets: N-body MNIST, a synthetic dataset with chaotic behavior, and SEVIR, a dataset that consists of 384 km x 384 km spanning over 4 hours. Images in SEVIR are sampled and aligned across three channels (C02, C09, C13) from the GOES-16 advanced baseline imager, NEXRAD Vertically Integrated Liquid (VIL) mosaics, and GOES-16 Geostationary Lightning Mapper (GLM) flashes.
- **Methodology:**
    - **Model Architecture:** PreDiff has a general two-stage pipeline for training data.
        - LDM for capturing intrinsic semantics in data. To capture Earth’s long-term and complex changes, they instantiate the LDM’s core neural network as a UNet-style architecture based on Earthformer.
            - LDM adopts a two-phase training that leverages the benefits of lower-dimensional latent representations:
                - Training frame-wise variational autoencoder (VAE) that encodes pixel space into a lower-dimensional latent space.
                - Training a conditional DM that generates predictions in this acquired latent space.
        -  Inject prior knowledge of the Earth system by training a knowledge alignment network that guides the sampling process of the LDM. The alignment network parameterizes an energy function that adjusts the transition probabilities during each denoising step.
             - **Physical constraints:** They impose the law of conservation of energy in N-body MNIST and anticipated precipitation intensity in SEVIR. 
        -  Training of the knowledge alignment network is independent of the LDM training.
    - **Inputs and outputs:** The task is to predict the future VIL up to 60 minutes (6 frames) given 70 minutes of context VIL (7 frames) at a spatial resolution of 128 × 128.
    - **Loss Functions:** Combination of pixel-wise loss (MSE) and an adversarial loss for frame-wise autocencoder.
    - **Evaluation Metrics:** 
        - MNIST Compared against seven deterministic models (UNet, ConvLSTM, PredRNN, PhyDNet, E3D-LSTM, Rainformer, and Earthformer) with standard metrics like MSE, MAE, SSIM, and scores of Fréchet Video Distance (FVD).
        - SERVIR with CSI, FVD, continuos ranked probability score (CRPS)
- **Key Results:**
    - PreDiff with knowledge alignment substantially outperforms all baseline methods, and PreDiff without knowledge alignment
    - Effective in handling uncertainty, incorporating domain-specific prior knowledge.
    - The Nowcasting exhibit high operational utility.
- **Strengths:**
    - Nowcasting with PreDiff exhibits high operational utility.
    - Allows training lightweight knowledge alignment networks to explore various constraints and domain knowledge without the need for retraining the entire model.
- **Limitations:**
    - Evaluation metrics and benchmark datasets for precipitation nowcasting are still maturing.
    - Effective integration of physical principles and domain knowledge into DL models for precipitation nowcasting remains an active research area.
    - Quality of data can limit the ability to capture the true distribution, resulting in unrealistic forecasts under the guidance of prior knowledge.
- **Relevance:**
    - Represents a promising advance in knowledge-aligned DL for Earth system forecasting.
    - Use a dataset that integrates different types of information.
    - Emphasizes the importance of improving benchmarking.

### Paper 4: A Deep Learning-Based Methodology for Precipitation Nowcasting With Radar
- **Authors:** Chen et al. (2020)
- **Key Highlights:**
    - A novel deep learning neural network is proposed for precipitation nowcasting.
    - Group normalization is shown to be effective in training our model with high-resolution radar echo images.
    - An appropriate loss function is used to improve the relevant prediction performance.
- **Data Used:**
    - Radar reflectivity from WSR-88D from October 2015 to July 2018 with a temporal resolution of approximately 6 minutes.
- **Methodology:**
    - **Model Arquitecture:** 
        - ConvLSTM with star-shaped bridge (SB) architecture to transfer information across time steps. SB adds more information from the last time step to make the feature flow in multilayer ConvLSTM more robust.
        - The model includes Group Normalization (GN) applied on features.
    - **Evaluation metrics:** Compared against COTREC and ConvLSTM with cross-entropy at the loss functions with special multisigmoid loss trat is regarded as the differentiable CSI.
- **Key Results:**
    - The model achieves state-of-the-art performance.
    - Effectiveness of using GN as the normalization layer for precipitation nowcasting using radar echo images.
- **Strengths:**
    - Employ a special multisigmoid loss function as a simulation of CSI.
- **Limitations:**
    - The model suffers from a blurring effect, especially for longer future time steps. The more blurred the nowcasting, the more uncertainty of the system will grow with increasing lead time.
    - Focused solely on radar-based approaches, limiting insights into multispectral data integration.
- **Relevance:**
    - Highlights the importance of appropriate loss functions in precipitation nowcasting models.
    - Introduce techniques to refine convergence performance in optimization for ConvLSTM.


### Paper 5: A PredRNN: A Recurrent Neural Network for Spatiotemporal Predictive Learning
- **Authors:** Wang et al. (2022)
- **Key Highlights:**
    - Propose a recurrent network named PredRNN fir spatiotemporal predictive learning.
    - Propose a new curriculum learning strategy named reverse scheduled sampling, which forces the encoding part of PredRNN to learn temporal dynamics from longer periods of the context frames.
- **Data Used:** Regarding nowcasting, a dataset containing 10,000 consecutive radar maps recorded every 6 minutes in Guangzhou, China, was used. Also, Moving MNIST, KTH, Traffic4Cast, and BAIR were used for different applications. 
- **Methodology:**
    - **Model architecture:**
        - Predictive Recurrent Neural Network (PredRNN)
        - Spatiotemporal LSTM (ST-LSTM) serves as the building block of PredRNN. It leverages a pair of memory cells that are jointly learned and explicitly decoupled to cover long-term and short-term dynamics of spatiotemporal variations.
        - PredRNN learns non-Markovian dynamics from longer periods of observation frames.
        - Action conditioned PredRNN allows simulating the spatiotemporal variations of the environment in response to the actions of the agent in decision-making scenarios.
    - **Inputs and outputs:** Data is transformed to a pixel value and represented as 128x128 grayscale images. The dataset was divided into 7800 sequences for training and 1800 sequences for testing. Each sequence contains 10 input frames and 10 output frames, covering the historical data for the past hour and for the future hour.
    - **Loss functions:** MSE and MAE.
    - **Evaluation metrics:** Compared against TrajGRU, ConvLSTM, and MIM using CSI computed at different reflectivity thresholds.
- **Key Results:**
    - PredRNN significantly outperforms the other models in the visual quality of the generated future images. It makes more accurate predictions about the future.
    - Achieves the best performance over all CSI thresholds.
    - Achieves state-of-the-art performance on the synthetic and natural spatiotemporal datasets, including both action-free and action-conditioned predictive learning scenarios.
- **Strengths:**
    - Improves the state transition functions of convolutional RNNs.
    - Improves the training procedure to encourage the predictive network to learn non-Markovian dynamics from longer periods of observation frames.
- **Limitations:**
    - Limitation in dealing with the special cases of the long-tail distribution of the dataset.
    - Although PredRNN still achieves a better performance than the compared model in the forecast of future positions of the high-intensity areas, it cannot perfectly model the dynamics of the sparse echoes.
    - Multi-property model, so it may not be optimized for precipitation nowcasting.
- **Relevance:**
    - Provides an entire training scheme for, among other things, precipitation nowcasting.
    - Highlights the importance of future research in mitigating the long-tail effect by explicitly considering complex physical properties and combining them with deep learning models.

### Paper 6: Earthformer: Exploring Space-Time Transformers for Earth System Forecasting
- **Authors:** Gao et al. (2022)
- **Key Highlights:**
    - Introduced EarthTransformer, a space-time transformer for earth system forecasting.
    - Based on a generic, flexible, and efficient space-time attention block named Cuboid Attention.
    - Achieves significant performance on benchmarks about precipitation nowcasting and ENSO forecasting.
- **Data Used:** 
    - MovingMNIST and a newly proposed chaotic dataset called N-body MNIST to verify the effectiveness of cuboid attention and figure out the best design of Earthformer.
    - SEVIR and ICAR-ENSO for comparison with state-of-the-art models.
- **Methodology:**
    - **Model architecture:**
        - Earthformer is a hierarchical transformer encoder-decoder based on Cuboid Attention. Input observations are encoded as a hierarchy of hidden states and then decoded to the prediction target.
        - Generic cuboid attention layer that involves three steps: “decompose”, “attend”, and “merge”.
        - Global Vectors to help cuboids scatter and gather crucial global information.
        - Hierarchical Encoder-Decoder architecture that gradually encodes the input sequence to multiple levels of representations and generates the prediction via a coarse-to-fine procedure.
    - **Inputs and Outputs:**  
        - 10,000 sequences, each one having 2 digits moving inside a 64 x 64 frame. The dataset is split into 8100 samples for training, 900 samples for validation, and 1000 samples for testing. The task is to predict the future 10 frames for each sequence conditioned on the first 10 frames.
        - SERVIR precipitation nowcasting to predict the future VIL up to 60 minutes gives 65 minutes of context VIL.
    - **Feature Engineering:** Data is normalized between the range 0 to 1.
    - **Loss Function:** MSE for training all models.
    - **Evaluation metrics:** MSE and CSI evaluated and compared against UNet, ConvLSTM, PredRNN, PhyDNet, E3D-LSTM, and Rainformer.
- **Key Results:**
     - Able to more accurately predict the position of the digits with the help of global vectors on MovingMNIST.
     - Earthformer achieved the best overall permormance on precipitation nowcasting with SEVIR data and ENSO forecasting with ICAR-ENSO data.
- **Strengths:**
    - Global vectors bring consistent performance gain with negligible increase in computational cost.
    - Using a hierarchical coarse-to-fine structure can boost the performance.
- **Limitations:**
    - Earthformer is a deterministic model that does not model uncertainty.
    - The model generates blurry predictions of low perceptual quality and is lacking of valuable small-scale details.
    - The model is purely data-driven and does not take advantage of the physical knowledge of the earth system.
- **Relevance:**
    - Highlights the lack of appropriate metrics that measure the uncertainty component in Earth system forecasting models
    - Points out on adding physical constraints and ensembling the predictions from a data-driven model and a physics-based model.

## Comparison of Approaches
| Methodology/Technique | Key Strengths                   | Key Limitations                   | Example Papers                  |
|------------------------|---------------------------------|-----------------------------------|---------------------------------|
| SB-ConvLSTM          | Robust loss function     | Blurring in longer future time steps    | Le Chen et al. (2020)         |
| TrajGRU         | Skillful heavy rainfall event predictions      | Nowcasting is treated as a video task and does not include predictors of new convection   |  Xingjian Shi et al. (2017) |
| Conditional GAN | Fast and accurate location nowcasting | Heavy precipitation at long lead times remains difficult |  Ravuri et al. (2021) 
| PredRNN | Accurate predictions and visual quality | Limitation in dealing with the special cases of the long-tail distribution  | Wang Y et al. (2022) |
| Earthformer | Proficient prediction with low computational cost | Blurry predictions and purely data-driven | Gao et al. (2022) |
| PreDiff | Allows constraints and domain knowledge | Quality of data can limit the ability to capture the true distribution and lack of physical principles and domain knowledge | Gao et al. (2023) | 

## Challenges and Future Directions
- Combine multiple data resources to account for convection initiation.
- Lack of appropriate metrics that measure the uncertainty component in Earth system forecasting models
- Adding physical constraints and ensembling the predictions.
- Need of appropriate loss functions.
- Better predictions for extreme events.

## Conclusion
Deep learning models demonstrate transformative potential in precipitation nowcasting by improving spatial and temporal consistency, handling imbalanced data, and leveraging probabilistic frameworks. However, current evaluation metrics are insufficient for comprehensive validation. There is a growing need for better benchmarks and verification protocols tailored to nowcasting models. Additionally, the paper review emphasizes the need to incorporate domain-specific physical constraints for realistic predictions, a feature still underexplored in many methods and quality high-resolution datasets.

This area of research is very current and constantly improving, and advances in it can contribute to improved risk management and decision-making that will strengthen the region's climate resilience.
## Questions About Methodologies and ML Approaches

1. How to integrate different data resources and fields into the deep learning algorithms.
2. How to generate probabilistic predictions.
3. What are the best evaluation metrics, and why are existing metrics not the most appropriate?
4. Key differences between deep learning models.
5. Which physical constraints are introduced to the models, and how to do it effectively?
6. What is the best way to choose the input strategy?
7. How to handle noise in radar fields.
8. How to improve predictions of heavy precipitation.
9. If each model has its strengths and limitations, how to define the operational utility?
10. What are the future perspectives to improve models?
11. What is the importance of threshold loss functions?
12. What are the differences in performance resulting from different data transformations?

## References
1. Ravuri, S., Lenc, K., Willson, M. et al. Skilful precipitation nowcasting using deep generative models of radar. Nature 597, 672–677 (2021). https://doi.org/10.1038/s41586-021-03854-z
2. Shi, X., Gao, Z., Lausen, L., Wang, H., Wong, W., WOO, W., and Yeung, D. (2017). Deep Learning for Precipitation Nowcasting: A Benchmark and A New Model. https://doi.org/10.48550/arXiv.1706.03458
3. Gao, Z., Shi, X., Wang, H., Zhu, Y., Wang, Y., Li, M., and Yeung, D. (2023). PreDiff: Precipitation Nowcasting with Latent Diffusion Models. https://doi.org/10.48550/arXiv.2307.10422.
4. Chen, L., Cao, Y., Ma, L., & Zhang, J. (2020). A deep learning-based methodology for precipitation nowcasting with radar. Earth and Space Science, 7, e2019EA000812. https://doi.org/10.1029/2019EA000812.
5. Wang, Y., Wu, H., Zhang, J., Gao, Z., Wang, J., Yu, P., and Long, M. (2022) PredRNN: A recurrent neural network for spatiotemporal predictive learning. https://doi.org/10.48550/arXiv.2103.09504.
6. Gao, Z., Shi, X., Han, B., Wang, H., Jin, X., Maddix, D., Zhu, Y., Wang, Y., Li, M., (2022). Earthformer: Exploring space-time transformers for earth system forecasting. https://doi.org/10.48550/arXiv.2207.05833
