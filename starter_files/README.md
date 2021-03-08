
# Machine Learning Operations using Azure

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
*TODO* Provide a link to a screen recording of the project in action. 
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
   Certain deployed configuration setting can be changed dynmically at run time like enabling application insights. Certain deployed configuration settings like
   security options can not be changed dynamically at run time. After successful deployment, deployed model is shown in end point section as shown in below snap shot.
   ![End point snahpshot](https://github.com/venkataravikumaralladi/MachineLearingOperationsProject/blob/master/starter_files/ConsumedEndpointOutput.png)
    
 
## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
