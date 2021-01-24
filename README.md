# Delopying and exposing an AzureML auto trained model as a REST endpoint

In this project AzureML is used to train a model based on marketing data from a bank. A selection of the optimal model is made and deployed as a REST endpoint. Different methods of consuming the endpoint are show. Finally the creation of a complete end to end deployment is done using the Python SDK.

## Architectural Diagram

![Steps](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Steps.PNG "Steps")

## Key Steps

### Uploading a dataset and configuring an azureML run

In AzureML studio, a dataset containing marketing data is uploaded and a 'run' is configured where a dataset and a target column is specified. 

![Uploading a dataset and configuring an azureML run](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/AutoMLrun.PNG "Uploading a dataset and configuring an azureML run")


### using Automated ML to determine the best model

From all the training methods used by AutoML, the Voting Ensemble has the highest accuracy. 

![using Automated ML to determine the best model](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Trained_models.PNG "using Automated ML to determine the best model")


### Deploying the best model as a REST endpoint

The Voting Ensamble model is deployed and exposes a REST endpoint, with supporting swagger definition

#### Deploying the model
![Deploying the best model as a REST endpoint](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/EndpointReady.PNG "Deploying the best model as a REST endpoint")

#### Using the Swagger definition in SwaggerUI
![Using the Swagger definition in SwaggerUI](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/SwaggerJSON.PNG "Using the Swagger definition in SwaggerUI")

#### Consuming endpoint with endpoint.py
![Consuming endpoint with endpoint.py](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Endpointpy_result.PNG "Consuming endpoint with endpoint.py")

### Enable logging

To enable logging for the REST endpoint, a Python script is used that enables application insigts

![Enable logging](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Logs_output.PNG "Enable logging")

	
### Creating a publishing a pipeline

Using the iPython notebook, a pipeline is generated that is vissible as a graph in AzureML studio. 

#### Using the SDK to define a pipeline

![Creating a publishing a pipeline SDK](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Creating_pipeline_1.png "Creating a publishing a pipeline SDK")

#### The resulting peline in AzureML studio

![Creating a publishing a pipeline Result](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Pipeline.PNG "Creating a publishing a pipeline Result")


### Creating and/or sharing documentation and Swagger definition

Documentation depends on company standards, but would preferribly be accessable on a portal/intranet


## Screen Recording

Recording of all the steps taken in this project. Here are the timestamped subjects

### Uploading dataset

[![Uploading dataset](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=117)

### Configuring an azureML run

[![Configuring an azureML run](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=187)

### Selecting the best performing model to be deployed

[![Selecting the best performing model to be deployed](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=262)

### Enabelling logging

[![Enabelling logging](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=427)

### Swagger UI

[![Swagger UI](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=507)

### Consuming API endpoint with Python

[![Consuming API endpoint with Python](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=507)

### Notebook that does all the steps to setup an end to end pipeling using the Python SDK

Note: While recoding there where only a few minutes of time left in the Lab

[![Notebook that does all the steps to setup an end to end pipeling using the Python SDK](https://img.youtube.com/vi/rcyM-dMFxAU/0.jpg)](https://www.youtube.com/watch?v=rcyM-dMFxAU&t=773) 
