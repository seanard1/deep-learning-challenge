## Overview

Using a deep-learning neural network, we hope to train an algorithm that can recognize organization's applying for funding from Alphabet Soup that will likely to be successful with their business ventures. 

With a database of 34,000 previous applicants that have been given funding by Alphabet Soup, we can give the machine-learning model variables associated with the historical ventures to determine the criteria that suggests an applicant is likely to have success. 

The target variable for our model will be whether or not the previous venture was successful. Among the feature variables available to us are the type of application, industry or sector, classification, the type of organization and the amount of funding being requested. Some variables that won't go into the model include the name and identification of the organization, as well as others we will discuss later. Some of the variables have too much variety for one-hot encoding, so they are binned into an "other" category to catch-all after a certain point. 


## Results

As a starting point, we can pass in the scaled and one-hot encoded data (which has 44 input features thanks to one-hot encoding) into a neural network with two hidden layers (with eight and four nodes, respectively). Using a rectified linear activation function (ReLu), the model can accurately predict a successful applicant 73.29 per cent of the time. 

In an effort to optimize this model for greater accuracy, I used a few different approaches. First off, I further culled the available dataset based on closer analysis of the variables provided. First and foremost, the SPECIAL_CONSIDERATIONS information does not appear to be useful, as only 27 previous applicants have this status and 34,272 do not. Equally irrelevant is the STATUS column, which has 34,294 classified as active and only five as inactive. 

Perhaps a bit less straightforward is the decision to do away with the INCOME_AMT of the applicants. At first blush, this seems like extremely relevant information. But a closer look at the column reveals wide gaps in the ranges provided, as well as more than 70 per cent of all previous applicants reporting an income of zero. 

After culling the dataset from those additional columns, I used Keras Tuner to provide suggestions for a model to help improve the accuracy. That said, using the first and second "best" models provided by Keras Tuner (some of which involved a high number of nodes), as well as trying to original model with a different activation function (TanH), none of the new models were able to push past the 73 per cent barrier. 

- "Best" model from Keras Tuner (activation': 'tanh', 'first_units': 30,  'num_layers': 3, 'units_0': 15, 'units_1': 30, 'units_2': 20): 73.04 per cent.
- Original model with reduced input features ((activation': 'relu', 'first_units': 8,  'num_layers': 2, 'units_0': 4): 73.29 per cent.
- Second "Best" model from Keras Tuner ({'activation': 'tanh', 'first_units': 15, 'num_layers': 4, 'units_0': 25, 'units_1': 20, 'units_2': 25): 73.00 per cent


# Summary

The apparent upper limit of a neural network learning this dataset appears to be around 73 per cent. We failed to find a model that could push beyond that 73.39 per cent accuracy from the first model. Interestingly, this was the same result once we cleaned the additional columns from the dataset, which backs up my hypothesis that those variables were not helping the model as they were presented. 

In fact, the INCOME_AMT variable might be the key to building a more accurate neural network for this model. If it were available as a proper numerical value, rather than as a string to be one-hot encoded, it could help give the neural network a better path.