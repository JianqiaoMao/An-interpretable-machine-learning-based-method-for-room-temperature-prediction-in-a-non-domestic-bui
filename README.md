# Interpretable machine learning for HVAC predictive control: A case-study based implementation

## Overview

Energy efficiency and thermal comfort levels are key attributes to be considered in the design and implementation of a Heating, Ventilation and Air Conditioning (HVAC) system. With the increased availability of Internet of Things (IoT) devices, it is now possible to continuously monitor multiple variables that influence a user’s thermal comfort and the system’s energy efficiency, thus acting pre-emptively to optimize these factors. \textcolor{red}{To this end, this paper reports on a case study with a two-fold aim; first, to analyze the performance of a conventional HVAC system through data analytics; secondly, to explore the use of interpretable machine learning techniques for predictive control with the vision of realizing a trusted and autonomous HVAC system.} A new Interpretable Machine Learning (IML) algorithm called Permutation Feature-based Frequency Response Analysis (PF-FRA) is also proposed to quantify the contribution of each predictor in the frequency domain. Results demonstrate that the proposed model can generate accurate forecasts of short-term and long-term Room Temperature (RT) levels by taking into account historical RT information, as well as additional environmental and time-series features. Our proposed model achieves 1.73\% and 4.01\% of Mean Absolute Percentage Error (MAPE) for 1-hour and 8-hour ahead RT prediction, respectively. Tools such as surrogate models and Shapley graphs are employed to explain the model's global and local behaviors with a view to making the machine-made control decision trusted and reliable.

## Dataset

The data considered in this work was acquired from both indoor and outdoor sensors and system indicators of an HVAC system installed in an 11-story commercial office building in Athens, Greece between December 2017 and September 2020. The building did not employ any other sensors except the ones provided in the dataset. It is worth highlighting that this is not a new build and was constructed in the 1990s with some refurbishments in the HVAC system over the past decades. It is worth noting that for the results presented in this work, the data observations from February 29th, 2020 onwards are excluded from the analysis to avoid the inconsistency in user patterns that inevitably occurred during the breakout of the COVID-19 pandemic. With this in mind, the overall dataset was split into the following subsets: a training set covering the period from December 8th, 2017 to June 30th, 2019; a validation set covering the period from July 1st, 2019 to October 10th, 2019; and a test set covering the period from October 11th, 2019 to February 29th, 2020.

<div align=center><img src=https://github.com/JianqiaoMao/Interpretable-machine-learning-for-HVAC-predictive-control/blob/main/figures/table_dataset_description.png width=800 /></div>

## Framework of data acquisition, processing and modeling phases

The figure below depicts the framework adopted in this work from the data acquisition phase through to the interpretation of the machine learning model employed. The process starts with the collection of the data from different sensors including HVAC status indicators, as well as environmental data from indoor and outdoor sensors. After pre-processing the data and addressing challenges such as different sampling strategies and time misalignment, comprehensive Exploratory Data Analysis (EDA) is conducted to investigate the data distribution of the predictor and target variables, followed by stationarity and hidden pattern analysis. By recursively optimizing our feature engineering strategy based on knowledge discovery from the EDA process, we extract important information that is subsequently used in the predictive modeling phase.

<div align=center><img src=https://github.com/JianqiaoMao/Interpretable-machine-learning-for-HVAC-predictive-control/blob/main/figures/process.png width=800 /></div>

## Performance of Room Temperature Prediction

The figure below compares the finalized model’s predictions with the true room temperature series over the whole period with a detailed plot on the validation and test sets. It is observed that the model successfully forecasts the trends as well as most fluctuations despite failures for some extreme values.


<div align=center><img src=https://github.com/JianqiaoMao/Interpretable-machine-learning-for-HVAC-predictive-control/blob/main/figures/performance.png
 width=800 /></div>
 
To validate our proposed method, we also compare our predictive model’s performance with related studies [1][2] which have comparable settings and evaluation metrics. The table below shows that the proposed modeling method has a more satisfactory performance than the others for the short-term RT prediction. In terms of long-term RT prediction, our method also shows capability with certain performance decay, while the investigated work does not discuss it.

<div align=center><img src=https://github.com/JianqiaoMao/Interpretable-machine-learning-for-HVAC-predictive-control/edit/main/README.md
 width=600 /></div>




