# Presentation of NABMOS (NAtional Bicycle MOdal Shift) model (code confidential)

This page presents the NAtional Bicycle MOdal Shift (NABMOS), a tool for assessing the economic potential of bicycle decarbonization. This model estimates the modal shift to cycling and the CO2 reduction, by Etablissement Public de Coopération Intercommunale (EPCI), generated by the creation of cycling infrastructures and by density typology (INSEE, 2024). It generates performance indicators such as the number of tons of CO2 saved over the lifetime of the infrastructure, as well as the associated carbon abatement cost according to each INSEE territory typology: rural, peri-urban and urban. 
Bicycle modal share is predicted by the model on the basis of several explanatory variables detailed in the section below. CO2 savings are then calculated on the assumption that the increase in cycling modal share compared with 2021 comes solely from modal shift from the private car. 
The model presented here only forecasts the modal share in terms of the number of home-work journeys, so we use this as a proxy to estimate the modal share in terms of passenger-kilometres for all reasons. The extrapolation is based on national distributions taken from the Enquête Mobilités des Personnes (2019). As a result, the models and interpretations presented do not provide a sufficiently reliable estimate at the territorial level alone. The results could be refined with local surveys. 

The model is a python code encapsulated in an executable (CX_FREEZE), which runs locally on a computer, and the interface has been coded in Streamlit for greater fluidity of use. The interface is in French and comprises 5 tabs:
The model is written in Python and encapsulated in an executable (CX_FREEZE), which runs locally on a computer, while the interface has been coded in Streamlit for ease of use. The interface is in French and comprises 5 tabs:

- A “Présentation de l'outil” tab to briefly describe the model's purpose, scope and limitations.
- A “Modèles statistiques” tab presenting the different models used, along with their parameters and the usual associated statistical tests (Jarque-Bera for normality of residuals, collinearity, kurtosis and skewness...).
- A “Hypothèses générales du modèle” tab, which reports on the basic assumptions used as a reference scenario.
- An "Modèle interactif" tab for producing and exporting model result graphs in real time. You can choose the length of cycle paths, the construction schedule, the longevity of the infrastructure, the price of a one-way kilometer, the emission factor and the occupancy rate of each vehicle.
  
![](pictures_nabmos/nabmos.png "Interactive model illustration (french)").

**More details in Methodology section**
