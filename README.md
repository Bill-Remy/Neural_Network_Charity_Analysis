# Neural_Network_Charity_Analysis

## Overview of Analysis

The purpose of this analysis is to develop a predictive binary model for a charitable to determine which applicants will be successful in deploying the funds for their project.

## Approach

The approach for this project will be to develop a neural netorwk(NN) to evaluate the likelihood of successfully deploying the funds from Alphabet Soup.  The model will consider the numerical elements and categorical data from the applicants.  The categorical data will be converted to numerical values and all data will be scaled using StandardScaler.   The initial starting point for the model is to allocate 33% of the data for testing and 67% for training the model.  The initial model parameters for the network will consist of two hidden layers with 100 and 50 nodes repsectively.  The Relu activation function will be used.  The model will trained on 25 epochs.

The target variable is "IS_SUCCESSFUL" from the imported data.  All other fields in the file were included either as numerical or categorical values converted to numerical via OneHotEncoder.

![image](https://user-images.githubusercontent.com/101779456/182060800-c26eb7ce-ea8b-481c-92f5-87dae67a3079.png)
![image](https://user-images.githubusercontent.com/101779456/182060856-ba319358-97db-4516-a699-0b8510b0d6f2.png)


## Initial Model Parameters - Results

The results from the intial run are show below.  Model accuracy on test data was 61% which is lower than desired.

![image](https://user-images.githubusercontent.com/101779456/182060735-bcbc5db0-fd95-4c45-bee6-89704a9963cc.png)
## Optimization Approach
In order to improve the performance of the model, Keras-Tuner will be used with the ability to search for best set of hyperparameters.  The routine for optimizing is shown below.

![image](https://user-images.githubusercontent.com/101779456/182252152-55e953d0-4a7d-49f9-b967-181f9725539c.png)


## Optimization Run #1
Base Model with Application type data removed.  Run with Keras-Tuner.  



### Results
![image](https://user-images.githubusercontent.com/101779456/182251753-d1a6422e-3fb7-452f-bba0-5ee330b4d07b.png)


## Optimization Run #2

Eliminated Application_type and Classification from the model.  Did not change any other parameters.  Run with keras-tuner.

Model parameters
![image](https://user-images.githubusercontent.com/101779456/182066112-4be4df47-8dc7-4563-b217-ad1dab976bf8.png)


### Results




## Optimization Run #3
Added back all columns and reduced test data to 30%.

### Results

![image](https://user-images.githubusercontent.com/101779456/182253955-1b25f6ce-f61d-4b6e-adc9-158f08aa2c69.png)


Optimization Run #4
All original columns, converted and scaled, test data at 30%, max_epochs at 30 in tuner.

### Results

![image](https://user-images.githubusercontent.com/101779456/182255826-1d85f496-b752-4d84-ad7e-ebb7c82eafb9.png)


