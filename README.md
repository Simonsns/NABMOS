# Presentation of NABMOS model (code confidential)

The NABMOS model combines 3 econometric models for 3 types of territory (excluding the Greater Paris Metropolis, which benefits from a separate model).
The urban and suburban sectors are linear log-log regressions. 
It should be noted that the 95% confidence interval is significant, especially in the peri-urban sector, as the variability of observations is very high. Thus. The trend in the peri-urban and urban sector could be significantly higher than the estimates.
The rural sector is modeled by a regression with spatial lag, which also takes into account the bicycle modal share of neighboring areas to explain the bicycle modal share of the study area. We used this model because conventional econometric models (linear regression, logistic regression, etc.) were unable to adequately predict observations at the rural level. Taking the spatial dimension into account enables us to better appreciate regional dynamics, and to better approximate their trends.

## Urban and peri-urban models: log-log linear regression and ordinary linear regression

The form of the regression for the urban and peri-urban models is as follows

$$\ln (y) = \alpha + \sum_i \beta_i \ln(x_i) + \varepsilon $$

Where : 
	- $y$ : the variable of interest, in this case cycle path length.
	- $x$ : the chosen explanatory variables.
	- $\alpha$ : the model calibration constant.
	- $\beta$ : the regression coefficients associated with each explanatory variable.
	- $\varepsilon$ : the associated error, following a normal distribution $N(0,σ^2)$.

The Paris model has a similar form, but without the use of the logarithm on both terms of the equation.

## Rural model: Regression with spatial lag

The rural model is a spatial autoregressive regression model, which takes into account the effect of neighboring modal shares of close neighbors in the study area (in this case, n = 5). 
Thus, the form of the regression is as follows:

$$ y_{it} = \alpha + \rho\sum_{i \neq j} w_{ij} y_{jt} + \beta_{it} x_{it} + \varepsilon_{it} $$

With : 
	- $y$ : the variable of interest, in this case linear cycling ;
	- $x$ : the chosen explanatory variables (described in Table 1) ;
	- $α$ : the model calibration constant;
	- $β$ : the regression coefficients associated with each explanatory variable;
	- $\varepsilon$ : The associated error, following a normal distribution $N(0,σ^2)$ ;
	- $\rho$ : The coefficient modeling the impact of the modal share of neighboring areas on y ; 
	- $w$ : The indicator function of the neighboring zone.

Spatial interaction is modeled here through the introduction of the spatially lagged dependent variable $\sum_{i \neq j} w_{ij} y_{jt}$, hence the name “spatial lag”.

The two graphs illustrate the comparison between the actual values in blue and the predictions of the peri-urban model on a logarithmic scale, represented by the bisector, in orange. In essence, both graphs show satisfactory performance, with a majority of points aligned close to the bisector: 

	R² = 0.51 for the urban model ;
	R² = 0.33 for the suburban model.

This reflects our ability to estimate modal shares well in a large proportion of cases. However, the prediction of extreme values seems more difficult.
In the extreme value ranges, predictions tend to deviate more from actual values. This phenomenon seems to be linked to the scarcity of data in this range. Nevertheless, it can be observed that for large values of cycle path length, predictions remain generally accurate, although a few points show a slight dispersion. 
A notable observation is the greater dispersion of actual values around the bisector, which might suggest that explanatory variables are missing. As the statistical analysis has shown that the other available data are not satisfactory explanatory variables, it would be necessary to collect additional data to test other explanatory variables (e.g. relief).
Some points far from the bisector could also be statistical artefacts (outliers), introducing disproportionate errors into the estimates.
The four points framed in blue are statistical artefacts (islands). They are therefore not included in the analysis here.

## Paris Model

The Greater Paris model was designed to model travel behavior more precisely within the EPCI “Métropole du Grand Paris” exclusively. 
It is based on Geographically Weighted Regression (GWR), in response to the observation that a regression model covering the whole territory may not adequately capture local variables.
The model consists of ordinary linear regression, with parameters for neighboring areas weighted according to distance from the area of interest. For example, observations located 1 km from the study area will be more structuring than those located 10 km from the area of interest.
By maximizing the AICc, we estimated that our observation boundary would be equal to 70 neighbors around the zone of interest. 
Thus, the heterogeneity of observations in the zone helps explain the significance of the 4 parameters included in the model (in the table Description of individual behaviors, in the Methodology section).
