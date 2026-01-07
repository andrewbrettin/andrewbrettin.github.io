---
permalink: /research/
title: "Research Projects"
classes: wide
---

## Estimating temperature and precipitation uncertainties with quantile neural networks
<div class="research-section" markdown="1">
  <div class="research-content" markdown="1">
  The climate system is highly chaotic and unpredictable. As a result, a significant portion of climate science research focuses on **constraining climate uncertainties** under changing conditions. In light of these uncertainties, we propose a data-driven probabilistic technique, a type of quantile neural network, for quantifying uncertainties that requires few assumptions and has a straightforward implementation. Using a synthetic dataset, **we demonstrate the advantages of this quantile neural network** over field-standard baselines that make stronger assumptions, such as linear relationships between inputs and outputs and normally distributed uncertainties. We then apply this technique to weather station temperature data and satellite observations of precipitation, **finding that daily maximum temperatures are well described by nonlinear relationships** with normally distributed uncertainties, whereas **precipitation depends significantly nonlinearly on the model inputs and exhibits non-normal statistics**. This work shows how quantile neural networks can be easily implemented to gain a more accurate representation of uncertainties in the geosciences.
  </div>
  <figure class="research-figure">
    <img src="/assets/images/timeseries_pred.png" alt="Quantile neural network results">
    <figcaption>Timeseries of predicted distributions of sea level nontidal residuals for a tide gauge at Stone Harbor, New Jersey (39.1°N, 74.8°W) from October 1–November 15, 2020 by our quantile regression neural network. The target timeseries is given by the black line. Gray shading indicates time periods of impacts form Hurricane Delta (October 11–12) and Tropical Storm Zeta (October 29–31), respectively.</figcaption>
  </figure>
</div>

<div class="research-meta" markdown="1">
✅ ***Outcomes:* [Preprint](https://andrewbrettin.github.io/assets/files/158a7a8ab60415feaea6ec98680ebca5.pdf) • [Code](https://github.com/andrewbrettin/quantile_ml)**

🔧 *Tools:* Python • Bash • git/GitHub • Singularity (containerization) • Dask • GCP • Pytorch • Lightning AI • Weights & Biases (optimization/experiment tracking) 

💪 *Skills:* HPC • [quantile regression](https://doi.org/10.2307/1913643) • [maximum likelihood estimation](https://doi.org/10.1109/ICNN.1994.374138) • probabilistic modeling • uncertainty quantification • probabilistic metrics (CRPS, calibration) • numerical methods
</div>

## Learning efficient forecasts for regional sea surface height dynamics
<div class="research-section reverse" markdown="1">
  <div class="research-content" markdown="1">
  Sea surface height forecasts are impacted by many different sources of uncertainty due to the highly nonlinear and chaotic dynamics of the climate system. Thus, many different approaches are commonly taken to develop forecasts, ranging from coupled-model physics simulations to data-driven approaches trained on observational products. Over the past few decades, [Linear Inverse Modeling](https://doi.org/10.1175/1520-0442(1995)008%3C1999:TOGOTS%3E2.0.CO;2) (LIM) has become an eminent statistical technique for building forecasts in the climate sciences, at times producing [forecasts](https://doi.org/10.1088/1748-9326/abe781) [that can outperform](https://doi.org/10.1175/JCLI-D-20-0209.1) numerical simulations. However, it assumes that the modeled system is described by linear dynamics, an often strong assumption for the chaotic and complex climate system.

In this study, we **leverage the theory of non-linear dynamical systems** ([Koopman operator theory](https://doi.org/10.1073/pnas.17.5.315)) **to develop better forecasts** than LIM. We train a **Convolutional Neural Network (CNN)** autoencoder with a dynamical propagator in the latent space (a “[Koopman Autoencoder](https://doi.org/10.1038/s41467-018-07210-0)”) to produce regional sea surface height forecasts. **This approach exploits both practical and theoretical limitations** of LIM. First, learning the timestepping and dimensionality reduction simultaneously results in better forecasts than with LIM, where dimensionality reduction and propagation are learned sequentially. Thus, the dimensionality reduction is performed in a way that is explicitly advantageous for forecasting. Second, our CNN autoencoder transforms the representation of high-dimensional, nonlinear dynamics into a low-dimensional latent space with linearized dynamics. This makes our model more interpretable. The Koopman autoencoder results in **forecast performance gains of 5-10%** over linear inverse models using models of similar complexity.
  </div>
  <figure class="research-figure">
    <img src="/assets/images/koopman_diagram.png" alt="Quantile neural network results">
    <figcaption>Illustration of the Koopman Autoencoder. The encoder maps the system state to a low dimensional embedding, while the decoder transforms the encoded prediction back into state space. Dynamics are represented by the low-dimensional linear propagator (which approximates the Koopman operator).</figcaption>
    <img src="/assets/images/pacific_koopman_skill.gif" alt="Koopman autoencoder skill">
    <figcaption>Skill of the Koopman Autoencoder relative to LIM for a variety of different forecasting leads. Using the Koopman Autoencoder results in persistently improved performance in the low-latitude Pacific.</figcaption>
  </figure>
</div>
<div class="research-meta" markdown="1">
✅ ***Outcomes:* [Article, *Geophysical Research Letters*](https://doi.org/10.1029/2024GL112835) • [Code](https://github.com/andrewbrettin/koopman_autoencoders_ssh_prediction)**

🔧 *Tools:* Python • Bash • Singularity (containerization) • git/GitHub • Dask • Pytorch • Lightning AI • Weights & Biases (experiment tracking) 

💪 *Skills:* PCA • Convolutional Neural Networks (CNN) • Autoencoders • Distributed data parallelism (DDP) • Statistical-dynamical modeling (LIM, dynamic mode decomposition)
</div>


## Identifying sources of sea level predictability using uncertainty permitting machine learning with explainable AI
<div class="research-section" markdown="1">
  <div class="research-content" markdown="1">
  **Reliable sea level forecasts on daily-to-seasonal timescales (1–180 days) are hindered by numerous sources of uncertainty** from both the atmosphere and ocean. This time horizon is [notoriously challenging for forecasting](https://www.notion.so/Projects-summaries-2e1a9ead675e80288f68c0286c1090a5?pvs=21), as predictability from the atmosphere is lost but longer-term sources of predictability from the ocean have yet to emerge. Nevertheless, the daily-to-seasonal time horizon is critical for municipalities to mitigate potential damages from [high-tide tide flooding](https://www.notion.so/Projects-summaries-2e1a9ead675e80288f68c0286c1090a5?pvs=21).

  One approach to improving forecasts on this time horizon is to focus on intial conditions which can extend predictability horizons. Identifying these initial conditions which are inherently more predictable can allow forecasts to be made on time horizons that would not normally be considered. In this study, we leverage [mean-variance estimation networks](https://doi.org/10.1109/ICNN.1994.374138) to identify state-dependent sources of predictability for sea level using the [Community Earth System Model (CESM2)](https://www.notion.so/Projects-summaries-2e1a9ead675e80288f68c0286c1090a5?pvs=21) [Large Ensemble dataset (LENS2)](https://doi.org/10.5194/esd-12-1393-2021). **Using these uncertainty-quantifying neural networks and interpretable machine learning procedures (Explainable AI), we examine how the dominant drivers of predictability change over a range of different forecast leads at a variety of locations.** For instance, while local persistence drives dynamic sea level predictability at Guam (14°N, 145°E) on shorter forecast lead times, as the forecast lead is extended to seasonal timescales, propagating Rossby waves emerge as a dominant source of predictability. This study shows how uncertainty-quantifying machine learning can be used to help identify sources of predictability on a range of forecasting leads and could help improve forecasts crucial to administrators.
  </div>
  <figure class="research-figure">
    <img src="/assets/images/uq_predictions.png" alt="Quantile neural network results">
    <figcaption>Example uncertainty-quantifying forecasts of dynamic sea level at Guam (14°N, 145°E) at leads of 20 days. Predicted distributions (colored lines) indicate the normal distributions parameterized by the predicted mean and standard deviation outputted by the network. The climatological distribution of sea levels are shown in the gray histogram.</figcaption>
  </figure>
</div>

<div class="research-meta" markdown="1">
**✅ *Outcomes:* [Article, *Artificial Intelligence for the Earth Systems*](https://doi.org/10.1175/AIES-D-25-0014.1) • [Code](https://github.com/andrewbrettin/zos_predictability_aies)**

🔧 *Tools:* Python • Bash • xarray • Dask • Pytorch 

💪 *Skills:* Uncertainty quantification • Parallel computing • HPC • [mean-variance estimation networks](https://doi.org/10.1109/ICNN.1994.374138) • Explainable AI (integrated gradients)
</div>




## Exploring the nonstationarity of sea level probability distributions 
<div class="research-section reverse" markdown="1">
  <div class="research-content" markdown="1">
  Changes in the shape of the probability distribution of geophysical variables can significantly impact the occurrence of extremes. Therefore, understanding and **quantifying these changes is paramount to understanding changing risks** under rising seas. In this collaboration, we propose a theoretical framework for quantifying changes in probability distributions, modifying an approach by [McKinnon and Rhines (2016)](https://doi.org/10.1002/2016JD025292) to improve interpretability.
  </div>
  <figure class="research-figure">
    <img src="/assets/images/ishigaki.png" alt="Changing sea level distributions">
    <figcaption>Illustration of the Koopman Autoencoder. The encoder maps the system state to a low dimensional embedding, while the decoder transforms the encoded prediction back into state space. Dynamics are represented by the low-dimensional linear propagator (which approximates the Koopman operator).</figcaption>
  </figure>
</div>

<div class="research-meta" markdown="1">
**✅ *Outcomes:* [Article, *Environmental Data Science*](https://doi.org/10.1017/eds.2023.10)**

🔧 *Tools:* Python • R • scipy • statsmodels • xarray

💪 *Skills:* Quantile regression • probability theory • Extreme value theory • asymptotics
</div>