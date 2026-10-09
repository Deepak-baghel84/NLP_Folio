
## Web Threat Detection



using this we can identify the malicious websites and prevent from the frauds like someone send you need to pay this much of amount on this site else your account get suspended, you won something to crab the prize you have to pay this much of amount.


what is SharePoint in enterprises to keep the data, collaborate with the data.


Feature engineering is part of data preprocessing.
There are multiple steps related to data like,
ETL, data parsing, Data ingestion, data cleaning, data wrangling, feature engineering, data preprocessing, data transformations.

Complete process is same for the gen ai like core ml, only the training part got differ mainly, (data related part will be the same and evaluation).

Application(Project) development is one thing but scaling, optimizing and enhancements are the major things need to do in projects. like how you reduce latency(time taken to load document) ,cost of llm etc.
(Ai system design)


1 = yes , 0 = no ,  -1 = unknown

predictor file for inferencing part : means testing(predicting) over the trained model


screenshot _,48, 150 min

workflow: we have data in csv format we load the data then train a model using xgboost or Ann then save the trained model as .pkl file. then load the model and does inferencing or predictions.


python -m inference.predictor



Working of predictor-->web extractor:

user passes any website URL then request goes to web extractor(separate module) which using beautiful soup extract all the required features(30 existing features) then we pass to a validator(method) to check all features are exist or null then validate. Then all features will passes to the model(which we trained and loaded as .pkl file) and get inference which gives us the probability of legit, phishing based on that we return the response.





mlflow : Generally used for the tracking application, keep the information of complete pipeline, what metrices we capturing, what model we are training. Its like Lang smith .
Langsmith is easy to implement like simply using a api key but for mlflow we need to write code some classes and functions.


interview q in there.



run mlflow ui, given commands documents.
all the logs, training part will be saved over the mlflow and can be track and visible over there. it is open source platform.
we get the complete overview of the ui, pipeline, logs no need to check code again and again.
precision, accuracy, f1 scire, recall and hyperparameters(parameters) used during training visible there


screenshot: 120, 204

Remember:
On which port Fastapi, Flask run how to pass custom port.
port mapping is very important in docker 8000(docker port), 8080(local port)



Deployment:
Automatic load balancer(alb) + Api Gateway + Lambda + ui over the s3(static website) ==> For routing the Api
 App runner

Port Mapping: Docker image run inside a container( it is a vm) which contains some port address, so currently our application is running in this port and we want to run it over the internet/browser for that we map the docker port to internet port.


screenshot:  55


for mvp and quick deployment use : App runner or elastic-beanstalk


all information about deployment


Roles and policies : How different services will interact with each other for that need to define some incline or other policies or roles.
