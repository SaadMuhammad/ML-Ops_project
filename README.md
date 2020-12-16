*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.


# Operationalizing Machine Learning - Project 2

*TODO:* Write an overview to your project.

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 


## Key Steps

1. (Optional Part) Verified that az is enabled in terminal and performed az login via gitbash. Installed the Azure ML extension. Didn't work on creating 'Service Principle' since all the work has been done in labs. Few steps  performed for this part are shown below

![Screenshot](https://github.com/SaadMuhammad/ML-Ops_project/blob/main/Snapshots/Az%20help.PNG)

![Screenshot](Az help.PNG)

![Screenshot](az login.PNG) 

![Screenshot](add extension.PNG) 

2. Dataset has been registered on ML Studio
-dataset scn
Auto Ml experiment has been completed
-automl-run1
best model is voting ensemble having accuracy of 0.91927
-automl-run
showung run of different models and their performance
-best-model
best model other metrics details are as follows
-best-model1

3. application insights were not set to true during deployment, as shown below
-app-insights-false
appling logs.py to set the application insights to true
-logs-py1
-logs-py2
-logs-py3
-logs-py4
after applying 'logs.py' on terminal we set the app insights to true as shown below
-app-insights-true

4.swagger.json was downloaded from the Azure ML Studio. Swagger is used to interact with the HTTP REST API endpoint documentation. 'swagger.sh' will download the latest Swagger container, and it will run it on our specified port. 'serve.py' will start a Python server on port specified
-swagger1
-swagger2
-swagger3
-servepy1
-swagger-9000
-swagger-get1
-swagger-local
-swagger-post
-swagger-post1

5. After model is deployed, used the updated 'endpoint.py' script to interact with the trained model. A 'data.json' file is created as response to HTTP REST API endpoint
-endpoint1
Apache Benchmarking is used to benchmark the deployed model, following is the output
-benchmarksh1
-benchmarksh2
-benchmarksh3
-benchmarksh4

6. Now we will perform all the above steps on Jupyter using Python SDK as a pipeline.
-pipelinerun-sdk
endpoint creation via the pipeline process
-pipeline endpoint
run in progress
-pipelinerun-studio
Published pipeline overview
-rest-pipeline
Use Rundetails widget
-pipelinerun-completewidget
Finally the scheduled run
-pipeline-submit2

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:
in progress
## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
