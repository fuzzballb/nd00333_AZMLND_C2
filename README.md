# Deplopying and exposing an AzureML auto trained model as a REST endpoint

In this project AzureML is used to train a model based on marketing data from a bank. A selection of the optimal model is made and deployed as a REST endpoint. Different methods of consuming the endpoint are show. Finally the creation of a complete end to end deployment is done using the Python SDK.

## Architectural Diagram

![Steps](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Steps.PNG "Steps")

## Key Steps

### Uploading a dataset and configuring an azureML run

In AzureML studio, a dataset containing marketing data is uploaded and a 'run' is configured where a dataset and a target column is specified. 

![registerd datasets](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/1_1_registerd-dataset.PNG "registerd datasets")

![dataset details](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/1_dataset-available.PNG "datasets details")

![configuring an azureML run](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/AutoMLrun.PNG "configuring an azureML run")

### using Automated ML to determine the best model

From all the training methods used by AutoML, the Voting Ensemble has the highest accuracy. 

![using Automated ML to determine the best model](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Trained_models.PNG "using Automated ML to determine the best model")

### Deploying the best model as a REST endpoint

The Voting Ensamble model is deployed and exposes a REST endpoint, with supporting swagger definition

#### Deploying the model
![Deploying the best model as a REST endpoint](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/EndpointReady.PNG "Deploying the best model as a REST endpoint")

#### Using the Swagger definition in SwaggerUI

Using Swagger UI we can see the endpoints and expected data format for those endpoint.

![Using the Swagger definition in SwaggerUI](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/SwaggerJSON.PNG "Using the Swagger definition in SwaggerUI")

![The SwaggerUI won't allow the actual call](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/3_http_server_issue.PNG "The SwaggerUI won't allow the actual call")

#### Calling the endpoint with curl command 

To see if the proposed crul command of the Swagger file works, Here we are directly making a post request with curl 

![Calling endpoint with curl command](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/Call_to_endpoint_curl.PNG "Calling endpoint with curl command")

#### Consuming endpoint with endpoint.py

Calling the endpoint from a python sript also works

![Consuming endpoint with endpoint.py](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Endpointpy_result.PNG "Consuming endpoint with endpoint.py")

### Enable logging

To enable logging for the REST endpoint, a Python script is used that enables application insights, then we check the UI to see if logging is actually enabled

![Enable logging](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Logs_output.PNG "Enable logging")

![Check UI to see that logging is enabled](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/2_application_insights_true.PNG "Check UI to see that logging is enabled")

### Creating a publishing a pipeline

Using the iPython notebook, a pipeline is generated that is visible as a graph in AzureML studio. 

![Pipeline overview in AzureML studio](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/4_Pipeline-overview-running-2.PNG "Pipeline overview in AzureML studio")

![Pipeline graph in AzureML studio](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/Published-pipeline-automl.PNG "Published Pipeline graph")

#### Using the SDK to define a pipeline

![Creating a publishing a pipeline SDK](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Creating_pipeline_1.png "Creating a publishing a pipeline SDK")

#### The resulting pipeline in AzureML studio

The pipelines generated by the SDK are visible in AzureML studio. Here we see the active pipelines and the published pipeline endpoint

![ML studio showing the scheduled run using Published Pipeline REST Endpoint](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/6_scheduled-run.PNG "ML studio showing the scheduled run using Published Pipeline REST Endpoint")

![ML studio showing the pipeline endpoint as Active](https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/Screenshots/Review/5_endpointstate_active.PNG "ML studio showing the pipeline endpoint as Active
")

### Creating and/or sharing documentation and Swagger definition

Documentation depends on company standards, but would preferably be accessible on a portal/intranet

## Ways to improve the model

First autoML gives a class balancing detection alert. This should be solved by supplying an equal amount of records that nave the label 'No' as the label 'Yes'. Currently there are 7.9 times as much records with a 'No' label as there are with the label 'Yes'

Secondly it is an option to train longer and maybe even try if the neural network option gives better results. 


## Screen Recording

Recording of all the steps taken in this project. Here are the timestamped subjects

### Screencast

[![Uploading dataset](https://img.youtube.com/vi/2GcoFIh7-6I/0.jpg)](https://www.youtube.com/watch?v=2GcoFIh7-6I)

1 Working deployed ML model endpoint
2 Deployed Pipeline
3 Available AutoML Model
4 Successful API requests to the endpoint with a JSON payload



See https://github.com/fuzzballb/nd00333_AZMLND_C2/blob/master/starter_files/aml-pipelines-with-automated-machine-learning-step.ipynb 
for an overview of the steps executed in the Notebook

