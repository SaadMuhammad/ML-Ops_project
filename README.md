

# Operationalizing Machine Learning - Project 2


This Project involves Installing of Azure Machine Learning Extension and create Service Principle (SP).Then we will create and complete experiment using Automated ML run using the Bank Marketing Dataset which is registered on the Azure ML Studio. It is then Deployed using Azure Container Instance (ACI) which will allow to interact with the HTTP API service, Published and consumed using Swagger. Then the endpoint is benchmarked using Apache benchmarking.

In the Second part we employed Pyhton SDK via Jupyter notebook to create, consume and publish a pipeline

The Dataset is a binary classification problem consist of 20 features with 32,950 instances 

## Architectural Diagram

This diagram involves following actions: installing Azure ML extension and creating service principle (this step is optional for the current project but it is a neccesary task performed when interatcing with Azure ML). Then we register the dataset provided to us, create compute cluster with specified information, now we use AutoML to find the best model for our dataset, after fnding the best model we will deploy it via ACI and enable application insights vis logs.py. Now we use swagger to interact with model. Then we consume the model via endpoints.py and finally used Apache Benchmark to becnhmark the deployed model.

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/Arch-Diag.PNG)


## Key Steps

1. (Optional Part) Verified that az is enabled in terminal and performed az login via gitbash. Installed the Azure ML extension. Didn't work on creating 'Service Principle' since all the work has been done in labs. Few steps  performed for this part are shown below

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/Az%20help.PNG)

                                  Authenticate and Logged via az command on gitbash                                 
![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/az%20login.PNG) 

                                     Verified that extension is added                     
![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/add%20extension.PNG) 

2. Dataset has been registered on ML Studio

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/dataset%20scn.PNG) 

Auto Ml experiment has been completed

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/Automl-run1.PNG) 

best model is voting ensemble having accuracy of 0.91927

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/Automl-run.PNG) 

showung run of different models and their performance

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/best-model.PNG) 

best model other metrics details are as follows

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/best-model1.PNG) 

3. application insights were not set to true during deployment, as shown below
-app-insights-false

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/app-insights-false.PNG) 

appling logs.py to set the application insights to true

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/logs-py1.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/logs-py2.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/logs-py3.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/logs-py4.PNG)

after applying 'logs.py' on terminal we set the app insights to true as shown below

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/app-insights-True.PNG) 

4. 'swagger.json' was downloaded from the Azure ML Studio. Swagger is used to interact with the HTTP REST API endpoint documentation. 'swagger.sh' will download the latest Swagger container, and it will run it on our specified port. 'serve.py' will start a Python server on port specified


![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger1.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger2.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger3.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/servepy1.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger-9000.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger-get1.PNG) 

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger-local.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger-post.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/swagger-post1.PNG)



5. After model is deployed, used the updated 'endpoint.py' script to interact with the trained model. A 'data.json' file is created as response to HTTP REST API endpoint

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/endpoint1.PNG)

Apache Benchmarking is used to benchmark the deployed model, following is the output

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/benchmarksh1.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/benchmarksh2.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/benchmarksh3.PNG)

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/benchmarksh4.PNG)


6. Now we will perform all the above steps on Jupyter using Python SDK as a pipeline.

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/pipelinerun-sdk.PNG)

endpoint creation via the pipeline process

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/pipeline-endpoint.PNG)

run in progress

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/pipelinerun-studio.PNG)

Published pipeline overview

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/rest-pipeline.PNG)

Use Rundetails widget

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/pipelinerun-completewidget.PNG)

Finally the scheduled run

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/pipeline%20submit2.PNG)


## Screen Recording
The Recording and details can be viewed here [link to Udacity Project 2 Recording].

[link to Udacity Project 2 Recording]: https://youtu.be/Ajm_u9C-blc

## Future Improvement Suggestions

1. Addition of model stacking and blending techniques in AutoML will be a very valuable addition. As this will provide independence in stacking or blending top performing models to further improve the mertics
2. Option to select/create multi layer deeplearning model or even pre-trained model to be utilized (transfer learning techniques) will be of great use here.
3. Custom imputations to fill missing values based on data to data scenario would be a game changer i.e. Imputations that fill missing values based on feature importance, correlations and other statistcal knowledge will enhance model performance surprisingly.
