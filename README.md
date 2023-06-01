# Airbnb Lising Price Prediction
## Objective
The objective of this project is to analyze the available data for the following:
- Characterize the different kinds of properties/listings in the data
- Predict price of a listing
### Data Overview
From Kaggle, we have the following data available for ~70k AirBnB listings in London UK:
- Property Identifiers: Property ID (numeric), property name, neighborhood, lat-long coordinates, licensed or not
- Host Details: Host ID (numeric), host name, number of listings the host has in the database
- Listing details: Room types, availability information, price, minimum nights for a 
### Method
<img width="612" alt="method" src="https://github.com/jren99/Airbnb-Prediction/assets/47071387/d16b119f-3d12-4eae-b317-8ec5eaf13904">

Price prediction at overall level:
- We use stratified sampling to retrieve 20% of the data as testing data, ensuring good representation of neighborhood categories and room types in test data
- We use stable regression to split the remaining 80% data into training data (60%) and test data (20%)

Clustering:
- We cluster the entire data set 
- We extract data for each cluster and divide the data randomly into training (80%) and test (20%) sets

### Interpretable Clusters
Optimal Classification Trees method is used to interpret clusters. 

|  Cluster  |                                                                                                                                                       Feature                                                                                                                                                      |
|:---------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| Cluster 1 | Mid-low neighborhoods, offering private or shared rooms                                                                                                                                                                                                                                                            |
| Cluster 2 | Listings in very expensive neighborhood (Camden, Westminster, Kensington and Chelsea), that offer either private or shared rooms; AND listings that offer entire homes or are hotel rooms in expensive/middle/low cost neighborhoods but are booked for the most part of the year (available <42.5 days in a year) |
| Cluster 3 | All other properties                                                                                                                                                                                                                                                                                               |
| Cluster 4 | Listings offering entire homes or are hotel rooms that are generally available (availability >201 days)                                                                                                                                                                                                            |
| Cluster 5 | Listings with private/shared rooms in mid-high/middle /low cost neighborhoods                                                                                                                                                                                                                                      |
| Cluster 6 | Listings that offer entire homes or are hotel rooms in mid-high neighborhoods and but are booked for most part of the year (<42.5 days in last year), or are in other neighborhoods but have very high  availability (between 42 to 201 days in a year)                                                            |
