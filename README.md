# Drone Flowering Predictions

This documents predicting the flowering time of maize plots from RBG drone images that were taken throughout the season. 

See the `DroneFloweringPredictions.Rmd` file or the knitted output [here](https://acperkins3.github.io/DroneFloweringPredictions.html) for the code used.

## Experiment

In 2021, there were ~1200 plots with ground truth data (which were used for model training) and ~5000 plots without training data (for which flowering time was predicted).

In 2022, there were ~2000 plots with ground truth data (for model training) and ~5000 plots without ground truth data (for prediction).

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/FieldsOutline.png" /></p>

In 2021, flights were conduted once per week up to flowering and then every other day during the peak of flowering itself.

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/PlotOverTime.png" /></p>

Flights in 2022 were similar, but there were fewer during the peak of flowering.

## Data

RGB images were summarized using eight vegetation indices at 13 quantiles. In addition, the canopy area as a proportion of the plot area was extracted, and so was the elevation of the vegetation and soil at different percentiles.

## Heritability

The heritability of the features varied over the course of the seasons

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/H2%20Over%20Time%202021.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>

## Prediction

Preliminary work suggested that LASSO regression worked best. See the `DroneFloweringPredictions.Rmd` file or the knitted html for the feature engineering, feature selection, and hyperparameter tuning.

## Accuracy

Spearman rank correlations between predicted and observed values in the test sets were high

2021:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/TestSetSpearman2021.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>

2022:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/TestSetSpearman2022.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>



Correlation between the two replications was a bit low in 2021. This might be due to the effects of the strong wind storm that lodged many of the plants before flowering.

2021:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/GDD%20Anthesis%20Rep%20Correlation%202021.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>

2022:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/GDD%20Anthesis%20Rep%20Correlation%202022.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>

Spatial effects were present in both years

2021:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/GDD%20Anthesis%202021.png"
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC" /></p>

2022:

<p align="center"><img src="https://raw.githubusercontent.com/acperkins3/Drone-Flowering-Predictions/main/Images/GDD%20Anthesis%202022.png" 
style = "object-fit:fill;
width: 60%;
height: auto;
border: solid 0px #CCC"/></p>
