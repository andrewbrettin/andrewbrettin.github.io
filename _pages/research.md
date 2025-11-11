---
permalink: /research/
title: "Research"
classes: wide
---

## Estimating temperature and precipitation uncertainties with quantile neural networks | [Article](https://www.proquest.com/docview/3223742845?pq-origsite=gscholar&fromopenview=true&sourcetype=Dissertations%20&%20Theses) • [Code](https://github.com/andrewbrettin/quantile_ml)
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 2rem 0; align-items: flex-start;">
  <!-- Left: Image with caption -->
  <div style="flex: 1; min-width: 200px;">
    {% include figure
      image_path="/assets/images/timeseries_pred.png"
      caption="*The quick brown fox jumped over the lazy dog.*"
    %}
  </div>
  <!-- Right: Text -->
  <div style="flex: 2; min-width: 200px;  font-size: 0.8em;">
  Due to the risks that climate variability and extremes pose, quantifying risks and uncertainties under given conditions is a general goal of many climate science problems. One approach to quantifying uncertainties in regression tasks which has gained traction in recent years is to train neural networks on the Gaussian maximum likelihood to predict the mean and standard deviation of a normal distribution. These <a href="https://doi.org/10.1109/ICNN.1994.374138">mean-variance estimation networks</a> have been used to <a href="https://doi.org/10.1029/2021MS002534">add uncertainty in stochastic parametrizations</a>, to <a href="https://doi.org/10.1029/2022GL098635">identify sources of predictability</a>, and to <a href="https://doi.org/10.1073/pnas.2207183120">estimate the time remaining until critical global warming thresholds are reached</a>. However, this approach assumes that uncertainties can be represented through normal distributions, which may not hold for highly non-Gaussian quantities such as precipitation or daily temperature maxima. On the other hand, <a href="https://doi.org/10.1257/jep.15.4.143">linear quantile regression</a> allows for the prediction of any non-Gaussian distribution, but it assumes linear functional dependencies.
  <br><br>
  In this study, we propose a quantile regression neural network for quantifying uncertainties. Our proposed quantile regression neural network includes two straightforward modifications to the loss function to (1) enforce equal accuracy for different quantiles of the distribution and to (2) minimize the occurence of degenerate predicted probability distributions. We evaluate this approach for estimating uncertainties on a suite of synthetic and observational datasets, comparing the predicted distributions against those made by linear quantile regression and mean-variance estimation networks to assess the relative importance of the linearity and Gaussianity assumptions.
  </div>
</div>

## Learning Propagators for Sea Surface Height Forecasts Using Koopman Autoencoders | [Article](https://doi.org/10.1029/2024GL112835) • [Code](https://github.com/andrewbrettin/koopman_autoencoders_ssh_prediction)
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 2rem 0; align-items: flex-start;">
  <!-- Left: Text -->
  <div style="flex: 2; min-width: 200px; font-size: 0.8em;">
    Sea surface height forecasts are impacted by many different sources of uncertainty due to the highly nonlinear and chaotic dynamics of the climate system. In light of these uncertainties, many different approches are commonly taken to developing forecasts, such as by using computationally intensive numerical models which directly simulate physics or through data-driven approaches trained on observational products to model dynamics. 
    <br><br>
    Over the past few decades, <a href="https://doi.org/10.1175/1520-0442(1995)008<1999:TOGOTS>2.0.CO;2">Linear Inverse Modeling</a> (LIM) has become an eminent statistical-dynamical technique for building forecasts directly from data in the climate sciences, at times producing <a href="https://doi.org/10.1088/1748-9326/abe781">forecasts</a> <a href="https://doi.org/10.1175/JCLI-D-20-0209.1">that can outperform</a> numerical simulations. Implementing LIM generally involves applying a linear dimensionality reduction to spatiotemporal datasets (for example, using principal component analysis) and then inferring the best-fit propagator in the latent space from the time-lagged covariance statistics of the latent state variables. However, it assumes that the modeled system is described by linear dynamics, an assumption which may not hold for the chaotic and complex climate system, posing challenges for LIM.
    <br><br>
    Recent data-driven approaches based on the operator-theoretic perspective of nonlinear dynamics have offered an alternative approach to modeling dynamics. In particular, in Koopman operator theory, nonlinear dynamical systems can be represented through the linear (but infinite-dimensional) Koopman operator which advances measurements of a dynamical system forward in time. In this study, we showed it was possible to develop a better low-dimensional propagator for regional sea surface height forecasts using a convolutional neural network autoencoder architecture inspired by Koopman operator theory which was originally proposed by <a href="https://doi.org/10.1038/s41467-018-07210-0">Lusch et al (2018)</a>. By learning the dimensionality reduction and dynamics simultaneously, the Koopman autoencoder produces better forecasts than when learning the dimensionality reduction and propagator separately. 
  </div>
  <!-- Right: Image with caption -->
  <div style="flex: 1; min-width: 200px;">
    {% include figure
      image_path="/assets/images/koopman_diagram.png"
      caption="*Illustration of the Koopman Autoencoder. The encoder maps the system state to a low dimensional embedding, while the decoder transforms the encoded prediction back into state space. Dynamics are represented by the low-dimensional linear propagator (which approximates the Koopman operator).*"
    %}
  </div>
</div>

## Identifying sources of sea level predictability using uncertainty permitting machine learning with explainable AI |  [Article](https://doi.org/10.1175/AIES-D-25-0014.1) • [Code](https://github.com/andrewbrettin/zos_predictability_aies)
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 2rem 0; align-items: flex-start;">
  <!-- Left: Image with caption -->
  <div style="flex: 1; min-width: 200px;">
    {% include figure
      image_path="/assets/images/uq_predictions.png"
      caption="*The quick brown fox jumped over the lazy dog.*"
    %}
  </div>
  <!-- Right: Image with caption -->
  <div style="flex: 2; min-width: 200px;  font-size: 0.8em;">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium. Integer tincidunt. Cras dapibus. Vivamus elementum semper nisi. Aenean vulputate eleifend tellus.
  </div>
</div>


## Exploring the nonstationarity of sea level probability distributions | [Article](https://doi.org/10.1017/eds.2023.10)
<div style="display: flex; flex-wrap: wrap; gap: 2rem; margin: 2rem 0; align-items: flex-start;">
  <!-- Left: Image with caption -->
  <div style="flex: 2; min-width: 200px;  font-size: 0.8em;">
    Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium. Integer tincidunt. Cras dapibus. Vivamus elementum semper nisi. Aenean vulputate eleifend tellus.
  </div>

  <!-- Right: Text -->
  <div style="flex: 2; min-width: 200px;">
    {% include figure
      image_path="/assets/images/ishigaki.png"
      caption="*Changes in distribution of JJA tide-gauge observations of sea level at Ishigaki, Japan (24.4°N, 124.2°E).*"
    %}
  </div>
</div>
