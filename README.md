## Geospatial Analysis

A project by Victor Alves, Kai Brown, Garrett Powell for DAT-210-01, taught by Dr. Narine Hall at Champlain College.

The purpose of this project is to determine if a prediction analysis trained using data from one geographic location can be applied to other locations to get accurate 
results. 
The goal is to create a prediction model that is reasonably accurate in one location and apply it to another location to compare its accuracy. 
The project involves two different datasets; each one contains demographic, psychographic, property and identity data on US households. One set contains data from households in one and the other contains data from households in another location (specific locations cannot be provided).
Factors that could affect the accuracy must also be identified. 

The first step in this project was to clean the data to make it possible to run a prediction analysis on it, utilizing Python's powerful mathematics & machine learning libraries, such as pandas and sci-kit learn. We accomplished this by writing code that inferred the type of each column in the data set and used an algorithm to fill in the missing data that was appropriate to that data type.
For boolean and string columns, this involved filling in the missing data randomly using existing values in a way that preserved the frequency of each value. 
For numeric columns, this involved filling in the missing data using the mean value for the column. 
Once the data was clean, we wrote code to train a prediction analysis model on the data. 

We created this model using a random decision forest, and we used it to predict whether a given person in the data set was a gardener. Only the features that were common between the two data sets were used to create the model. 
First, we trained and tested the model using the data from the second geographic location. 
The result was a reasonably balanced set of classes an a receiver operating characteristic curve with an area of 0.81. 
Next, we trained the model using the data from the first geographic location and tested it against the data from the second geographic location. 
The result was a similarly balanced set of classes and an almost identical receiver operating characteristic curve with an area of 0.83. 

Some of the data in these data sets are based on demographics that are predominately location-based. 
Variables such as the household income, tax rates, type of housing and living area and building value tend to vary based on the location. These types of variables are likely to be different between the first geographic location and the second, which could affect the accuracy of our models. 
However, variables such as whether the person is a collector, a sports fan, a pet owner, educated, a foodie, a music fan, etc. seem to be more universal human traits that are based on individual preferences rather than location. 
These types of variables seem to be the ones that contributed most to our model, with “foodie” ranking number one in both “gardener” variable summary reports from the two locations on BigML. 

Our conclusion is that under certain circumstances, a model trained in one geographic location can be applied to another location to get accurate results.
