# Machine Learning Operations using Azure

Table of contents
=================

<!--ts-->
* [Summary](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/README.md#summaryy)
* [Architectural Diagram](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/tree/master/starter_files#architectural-diagram)
* [Dataset](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/tree/master/starter_files#dataset)
* [Key steps](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/tree/master/starter_files#key-steps)
* [Screen recording](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/tree/master/starter_files#screen-recording)
* [Standout suggestions](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/tree/master/starter_files#standout-suggestions)
<!--te-->


## Summary

This project is part of the Udacity Azure ML developer Nanodegree program. In this project, we will use Azure to configure a cloud-based machine learning production model, deploy it, and consume it. ML model using AutoML in Azure. We will also create, publish, and consume a pipeline. This project provides hands on experience on automation. Automation is corepillar of dev ops, applicable to ML operations, i.e., we will automate from creating ML pipeline, publishing a pipeline so that external services can interact with them, and consume pipeline end point.

## Architectural Diagram
![Machine Learning Dev Ops](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/Summary.png)

ML consits of code + data which is different from general software project which consists only code. Building reproducible pipelines, configuring pipelines, configuring continious integration, continious deployment, consuming end point are all part of ML operations. Constant evaluation and monitoring with robust deployment is necessary for secured and reliable model.

Some of the tools we use for MLOps are Azure Ml Studio, Azure Python SDK, Jupyter note book, Swagger, Apache bench mark and terminal window. 

Pipeline automation is corepillar of MLOps. Pipelines help us in automating from creating ML pipelines, publishing pipelines so that we can use the pipelines in CI/CD process.
Published pipelines can be consumed by pipeline endpoint.

Data is constantly changing, business needs changes which requires model to be retrained. This can be achieved effectively by creating Azure pipelines. Azure pipelines can be deployed in CI/CD enviroment which can be trained and new model can be deployed 

## Dataset
![UCI Bank Marketing Azure Snapshot](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/RegisteredDataSetsSnapshot.png)
Data set used for this project is classic marketing bank dataset uploaded originally in the UCI Machine Learning Repository. The dataset gives you information about a marketing campaign of a financial institution in which we will have to analyze in order to find ways to look for future strategies in order to improve future marketing campaigns for the bank. Model will predict if customer will subscribe to fixed deposit or not.

## Key Steps
 
   ### Auto ML
   Constructing machine learning models is a complex and iterative process which might involve trying various algorithms, various parameter setting, feature engineering,
   performance measurement. Using AutoML, we can simply optimize preprocessing, feature engineering, model selection, hyperparameter tuning, and model ensembling to
   name a few in all in one simple abstract pipeline.
   To create new Automated ML run we have to fill following forms to specify data set to be used for model, training cluster, and select task (i.e., classification,
   or regression or time series analysis), how long to be run, to name a few.Auto ML will try various models and we can select best model for deployment.
   As we can see in below snapshot various models are evaluated and performance measure of model is shown. We can select best model for deployment.
   ![AutoML Run Completion snapshot](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/BestAutoMLmodel.png)
   
   ### Deployment
   Deployment is about delivering a trained model in to production so that it can be consumed by other. Configuring deployment setting means making choices on deployment
   configuration like cluster settings, authentication etc to name a few. Having good grasp of deployed envirnoment helps in selecting right deploy configuration settings. 
   Certain deployed configuration setting can be changed dynmically at run time like enabling application insights by running `logs.py`.
   Certain deployed configuration settings like security options can not be changed dynamically at run time.
   After successful deployment, deployed model is shown in end point section as shown in below snap shot.
   ![End point snahpshot](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/ConsumedEndpointOutput.png)
    
   ### Consuming deployed service
   Endpoints are excellent example of hot we consume deployed models. The end points allows other services to interact with deployed models.
   End points can be RESTFul API's (HTTP end point).
   Swagger is a tool that eases the documentation effort. Swager guides developers by specifying what inputs are accepted , what output is produced. 
   Azure provides a "swagger.json" that is used to creates a website that documents the HTTP end point for a deployed model.

   We use docker to install swagger in our image. This is done by running script `bash swagger.sh`. This script uses docker to download swagger-ui and
   start a local webserver "swagger-ui". swagger-ui is a tool that understands the swagger.json file format and visualizes the API definion contained in "swagger.json"

   Scirpt `serve.py` acts as a python HTTP server that will serve the contents of the current directory. This script will listen on port 8000. This will allow
   swagger service to interact with this and produce beautiful documentation.
   
   Service is consumed by running script `endpoint.py`.
   ![Swagger web interface](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/SwaggerSvcWeb.png)
   ![Swagger post info](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/SwaggerSvcPutInfo.png)
 
   ### Benchmark
   Bench mark is an accpetable performance measure which is required for base lining performance. Bench marking HTTP API's is used to find the average response time
   for a  deployed model.  There are other important metrics like requests per second, response time to name a few.
   Apache bench mark is an easy and popular tool for bech marking HTTP services. It is avilable as command line tool as "ab".
   Security keys input to be provided for `ab` command which is written in script `benchmark.sh`.
   ![Apache Benchmark](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/ApacheBenchmarkOutput.png)
   
   ### Pipe line automation
   Data is constantly changing, business needs changes which requires model to be retrained. This can be achieved effectively by creating Azure pipelines.
   Azure pipelines can be deployed in CI/CD enviroment which can be trained and new model can be deployed. This is implemented in  
   `aml-pipelines-with-automated-machine-learning-step.ipynb`.
   
   Pipeline automation is corepillar of MLOps. Pipelines help us in automating from creating ML pipelines,publishing pipelines so that we can use
   the pipelines in CI/CD process. Published pipelines can be consumed by pipeline endpoint. Below are snap shots are published pipeline.
   ![Pipe line creatioin snaphot](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/PipelineCreatedSections.png)
   ![Pipe line endpoint](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/PipelineEndpointCreated.png)
   
## Screen Recording
   
   Screen cast shows how we can get best model using AutoML, Working deployed ML model endpoint, deployed pipeline and succeful API requests to the end point 
   with a JSON payload. Screen cast link: https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/MLOPsProjScreenCast.mp4
    
## Standout Suggestions
  
  Explored the bank marketing data set. Want to make data set balanced before training. In this project I explored Azure Container Instance, I want to
  automate the deployment to Azure Databricks and Azure Kubernetes Service using Azure Machine Learning services.
  
  I want to try version-controlling code, by gradually moving code experiments in a notebook to a module that is imported at the beginning of each file.
  Using auto-reload plugins, we can make sure that these modules get automatically reloaded whenever we change them, without needing to restart your kernel.
