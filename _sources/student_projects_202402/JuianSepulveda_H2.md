# Data-Driven of Clud Properties: A Literature Review

## Introduction
Accurate prediction of precipitation intensity is crucial for both human and natural systems, especially in a warming climate more prone to extreme precipitation. 
subgrid-scale cloud structure and organization, which affects precipitation intensity and stochasticity at coarse resolution.
This organization, which can persist from a few hours to several days, can
modify atmospheric moisture distribution, radiation, and precipitation intensity.
Representing cloud microphysical processes in large scale atmospheric models is chal-
lenging because many processes depend on the details of the droplet size distribution (DSD,
the spectrum of droplets with different sizes in a cloud). 
Microphysical parameterizations
employing prognostic moments are known to suffer from structural uncertainty in their
representations of inherently higher dimensional cloud processes, which limit model fi-
delity and lead to forecasting errors. 

## Paper Reviews

### Paper 1: Data‐Driven Equation Discovery of a Cloud Cover Parameterization\
**Authors:** Arthur Grundner, Tom Beucler,  Pierre Gentine, Veronika Eyring\
**Key Highlights:**
-  Climate models exhibit long‐standing systematic biases related to cloud parameterizations. As cloud cover is directly used in the radiation and cloud microphysics parameterizations, its estimate directly influences the energy balance and the statistics of water vapor, cloud ice, and cloud water.
- Este es el otro

**Data Used:**
- Data used to tran and benchmark:\
Storm resvoling ICON simulations:  DYnamics of the Atmospheric general circulation Modeled On Non‐hydrostatic Domains (DYA-
MOND) project (Two campaings, 40 days, time resolution: 4 H, spatial resolution: 2.47 km).\ 
ERA 5: Observational informated data set. Cloud Cover and Temperature\

**Methodology:**

***Pre-procesing Data Set***
- Coarse‐grain the DYAMOND data to an ICON and select cloud cover pixels
- Other variables, take a three‐dimensional integral over the high‐
resolution grid cells overlapping a given low‐resolution grid cell.
- To instead ensure consistency between cloud
cover and the other model variables, manually set the cloud cover in the
high‐resolution grid cells to 100% when the cloud condensate mixing ratio exceeds 10− 6 kg/kg and to 0%
otherwise.
- Removing predominantly cloud‐free cells to mitigate a class imbalance in the output (“undersampling”
step)
- Split the data into a training and a validation set, the latter of which is used for early stopping. To
avoid high correlations between the training and validation sets, we divide the data set into six temporally
connected parts.
- Define 24 set features in 4 group: firts cotain atmospherical data, second: vertical derivates fo group 1, third: geometrical parameters.

***Data‐Driven Modeling***
-  Three traditional diagnostic schemes for cloud cover:  Sundqvist scheme,  Xu‐Randall scheme, Teixeira (optimize RMSE) and train the three NNs (cell‐, neighborhood‐, and column‐based NNs).
- Sequential Feature Selection (SFS) starts without any features and carefully selects and adds features to a given type of model (e.g., a second‐order polynomial) in a sequential manner.
- train a sequence of SFS NNs with up to 10 features. “Q3 NN”'s architecture has three hidden layers with 64 units each; it uses batch normalization and its loss function includes L1 and L2‐regularization terms following hyperparameter optimization.
-  Satisfy certain physical constraints (1) The cloud cover output should be between 0% and 100%; (2)
an absence of cloud condensates should imply an absence of clouds; (3–5) when relative humidity or the cloud water/ice mixing ratios increase (keeping all other features fixed), then cloud cover should not decrease; (6) cloud cover should not increase when temperature increases; (7) the function should be smooth on the entire domain.
- Error metrics MSE, R2 and Hellinger distance.
- Use Simbolic regresion to deriva a equation from cloud cover.

**Key Results:**
-  Modern symbolic regression libraries (PySR, GPGOMEA) allow us to discover interpretable equations that diagnose cloud cover with excellent accuracy (R2 > 0.9).
- SFS approach with NNs revealed an objectively good subset of features for an unknown nonlinear function: relative humidity, cloud ice, cloud water, temperature and the vertical derivative of relative humidity.
- PySR also learned to incorporate ∂zRH (vertical derivative of relative humidity) in its equation.
- Divide in 4 cloud regimes: cirrus, cumulus, deep convective and stratus.
- The equation is simple, performs well, satisfies physical principles, and outperforms other algorithms when applied to new observationally‐informed data.

**Strengths:**
- Studying the order of selected variables can gather intuition and physical knowledge. 
- Analytical scheme satisfies six out of seven physical constraints.

**Limitations:** 
- High computational cost.
- No guarantee of it truly being the best‐performing feature set due to the greedy nature of the feature selection algorithm.
- Trained data set do not represent some physical process: marine stratocumulus cloud and shallow convection (coarse vertical grid resolution)

**Relevance:** 
- Derived data‐driven cloud cover parameterizations from coarse‐grained global storm‐resolving simulation (DYAMOND) output.
- Major advantage of our best analytical scheme
is its ability to adapt to a different data set (in our case, the ERA5 reanalysis product) after learning from only a
few of the ERA5 samples in a transfer learning experiment
- Symbolic regression can complement deep learning by deriving interpretable equations directly from data.


### Paper 2: Implicit learning of convective organization explains precipitation stochasticity
**Authors:** Sara Shamekh,  Kara D. Lamb, Yu Huang,  Pierre Gentine
**Key Highlights:**

- They employ machine learning to implicitly learn subgrid-scale organization and develop a precipitation parameterization that incorporates these data-driven organization metrics.
- Machine learning has shown tremendous skill in analyzing images and their complex spatial structure and thus might be well suited to investigate 2D organization and as a hypothesis tool to demonstrate the importance of subgrid information to best reproduce precipitation.
- Organization metrics capture some aspects of the organization and can potentially be used to inform the coarse-scale variables
about subgrid-scale cloud patterns for predicting precipitation

**Data Used:**

- System for Atmospheric Modeling (SAM), which was run as a part of the DYnamics of the Atmosphere general circulation Modeled on Nonhydro-static Domains (DYAMOND) Phase 2 Intercomparison Projec: satial scale: 4.2 km, time step: 15 min.

**Methodology:** 

- Coarse-grain two-dimensional variables of SAM-DYAMOND by horizontally averaging to typical climate model resolution (for instance, 100 km).
- Discard all nonprecipitating and land pixels, thus to narrow the focus of this study down to predicting precipitation intensity over the tropical.
- Train a Baseline-NN (fully connected feedforward network) using PW (Precipitable Water), SST, qv2m (Specific Humidity), and T2m and org_NN based in organization metrics of clouds.
- learn
an implicit representation of organization that is most relevant
to precipitation prediction.
-  extract information
relevant to predicting precipitation from a high-resolution
field using a dimensionality reduction technique known as an
autoencoder. An autoencoder (AE) is a powerful nonlinear
dimensionality reduction approach.
- low-
dimension representation, i.e., a latent space, embeds optimal
information needed from the high-resolution field to reconstruct
precipitation.
- The organization metrics are invariant to rotation systems.
- The loss function is the Mean Square Error (MSE).

**Key Results:** 

-  The neural network cannot predict the variability of precipitation and underestimates precipitation extremes. But informed Networks have a better performance predicting precipitation extremes and spatial variability.
- The baseline-NN has a low skill in accurately predicting precipitation and its variability, even though the overall behavior of precipitation. 
- Organization metric can be predicted as a simple memory process from information available at the previous time steps.
- results demonstrate a significant
improvement in precipitation prediction with the inclusion of
org, suggesting that the subgrid-scale structure is potentially
an important piece of information currently missing in the
parameterization of convection and precipitation in climate
models.

**Strengths:** 

- data-driven organization variables, org, extracted from a
high-resolution field of PW were shown to carry the required
information needed to accurately predict precipitation at the
coarse scale. 

**Limitations:** 

- Convection triggered by the collision of cold pools (namely, areas of relatively low temperature generated by the evaporation of rain or melting of ice) is more likely to result in extreme precipitation.
- Mass-Flux convection in GCMs do not include any organization or interaction among convective updrafts, treating them as randomly
distributed convective plumes. 
- Cloud cover parameterization and their impact on radiation sometimes use some representations of organization, but these remain largely ad hoc.
- Precipitation exhibits strong stochasticity.

**Relevance:** 

- The inclusion of an organization metric in climate models might be important for more realistic predictions of precipitation extremes in a warming climate.
- Neural networks can emulate unresolved processes from resolved variables, as they can capture complexnonlinear behavior of a physical system.

### Paper 3: Reduced order modeling for linearized representations of microphysical process rates 
**Authors:** K.D. Lamb, M. van Lier-Walqui, S. Santos, H. Morrison
**Key Highlights:**
- data-driven reduced or-
der modeling can be used to learn predictors for microphysical process rates in bulk mi-
crophysics schemes in an unsupervised manner from higher dimensional bin distributions,
by simultaneously learning lower dimensional representations of droplet size distributions
and predicting the evolution of the microphysical state of the system.
-  deep learning based reduced-order modeling can be used to discover intrin-
sic coordinates describing the microphysical state of the system, where process rates such
as collision-coalescence are globally linearized.
-  the minimum number of independent variables required to represent the
DSD such that the process of collision-coalescence can be accurately predicted at
the next model time step.
- latent variables learned using data-driven dimensionality reduction tech-
niques correspond with the moments of the DSD typically used to parameterize
collision-coalescence
- process rates such as collision-coalescence be represented in this latent
variable space informative are latent variable and moment based representations of the DSD ????

**Data Used:** [What datasets were employed?]\
**Methodology:** 
- data-driven discovery of dynamics assumes that although X is high di-
mensional, the dynamics in fact evolve on some lower-dimensional manifold in the state
space. Much of the focus of recent work on data-driven discovery has been related to dis-
covering properties of this lower-dimensional manifold that most meaningfully encode
the dynamics of the higher dimensional system, using many discrete observations of the
state of the system.
**Key Results:** [Highlight the main findings]\
**Strengths:** 
- data-driven dimensionality reduction to determine optimal pre-
dictors for the evolution of the droplet size distribution due to the collision-coalescence
process using an unsupervised machine learning approach.

**Limitations:**
- Microphysical parameterizations are formulated based on assumptions about the functional form
of the distributions. Most bulk schemes use one, two, or sometimes three statistical mo-
ments of the DSD, typically M0 , M3 , and M6 , as these are equivalent to or proportional
to physically observable quantities– the number concentration, mass, and radar reflec-
tivity, respectively.
- bulk schemes artificially
separate precipitating and non-precipitating hydrometeor populations (for example, by
treating cloud droplets and rain droplets as two separate categories).
- Other aproach to microphysical schemes are computational expensive that de bin scheme.
- Have into account two microphysical process in warm clouds.
**Relevance:** 
- how such reduced order models can be applied to represent DSDs and microphys-
ical processes and what we can learn from these approaches

### Paper 1: Data‐Driven Equation Discovery of a Cloud Cover Parameterization\
**Authors:** Arthur Grundner, Tom Beucler,  Pierre Gentine, Veronika Eyring\
**Key Highlights:** [Summarize the paper’s primary contributions]\
**Data Used:** [What datasets were employed?]\
**Methodology:** [Summarize the techniques or models used]\
**Key Results:** [Highlight the main findings]\
**Strengths:** [What does the paper do particularly well?]\
**Limitations:** [What are the shortcomings?]\
**Relevance:** [How does this paper contribute to solving your problem?]\

### Paper 1: Data‐Driven Equation Discovery of a Cloud Cover Parameterization\
**Authors:** Arthur Grundner, Tom Beucler,  Pierre Gentine, Veronika Eyring\
**Key Highlights:** [Summarize the paper’s primary contributions]\
**Data Used:** [What datasets were employed?]\
**Methodology:** [Summarize the techniques or models used]\
**Key Results:** [Highlight the main findings]\
**Strengths:** [What does the paper do particularly well?]\
**Limitations:** [What are the shortcomings?]\
**Relevance:** [How does this paper contribute to solving your problem?]\



## Comparison of Approaches
| Methodology/Technique | Key Strengths                   | Key Limitations                 | Example Papers                  |
|:------------------------|:-------------------------------|--------------------------------|---------------------------------|
| Improved Sequential Features Selection (SFS) NN's with Symbolic Regresion | Symbolic regression can complement deep learning by deriving interpretable equations directly from data | Hight computational cost and high grade knowledge about input data  | Beucler et al. (2023) "Review ML for cloud and convection parametrization"; Grundner et al. (2022) "SFS Method"|
| Baseline-NN fully conncted feed forward network and Org-NN The encoder part of the autoencoder includes three one-dimensional convolutional layers followed by two fully connected layers.     | Learn about cloud organization metrics                            | not give information about physical process and mechanics for the memory in precipitable clouds                             | M. Janssens et al. (2021) "Organization metrics"; K. Lee, K. T. Carlberg (2020) "Theory of autoencoder" | 

| [Technique 2]         | ...                            | ...                              | Lush et al. (2018) "identify the eigenfunctions ofthe Koopman operator, which represents the dynamical system in a basis set where the
dynamics are linearized globally" | 

| [Technique 2]         | ...                            | ...                              | M. Janssens et al. | 



## Challenges and Future Directions
- Symbolic regression can complement deep learning by deriving interpretable equations directly from data, suggesting untapped potential in other areas of Earth system science and beyond.
- One obstacle in integrating subgrid-scale organization into parameterizations is determining how to obtain useful informa-
tion from these subgrid structures that can aid in approximating unresolved variables such as precipitation, convective mass flux, or radiation, which may be reliant on such an organization.
- In climate models, the modeling and representation of hourly
and subhourly precipitation extremes, which are dominated by
deep convective precipitation, continue to be one substantial
source of uncertainty.
-  is important to investigate the relevance of
subgrid-scale structure in predicting convective tendencies and
radiative cooling of the atmosphere to further improve data-
driven parameterizations.

- challenging to represent using only a few predicted state variables, as collision-coalescence
generally leads to a DSD that cannot be easily represented by a gamma function with
a single mode.


## Conclusion
Summarize the key takeaways from your review. Discuss how these insights will guide your work.

## Questions About Methodologies and ML Approaches

**Paper 1**
- Como es eso de consider polinomios de diferentes ordenes en el proceso de sequential feature selection?
- En que consiste SFS?
- Cómo aplicar el metodo de Simbolic Regresion Fit?
- Como funciona el metodo de auto-encoder?
- Qué signfica latent space?
-  Dynamical mode decomposition
(DMD) is alternatively used to identify coherent spatio-temporal structures in high di-
mensional dynamical systems by approximating modes and eigenvalues of the Koopman
operator.



## References
1. [Full citation of Paper 1]
2. [Full citation of Paper 2]
...
n. [Full citation of Paper n]