# Operationalizing Machine Learning

In this project, I have performed basically 2 steps:
1. Trained an AutoML classification model using Azure ML studio, on bank marketing dataset. And deployed the best model as a REST endpoint, and published it to be consumed by other applications. Also, documented the model using swagger UI.
2. Automated the above steps using Azure SDK pipeline interface in jupyter notebook. Saved the best model, and created a REST endpoint for the best model and finally scheduled an experiment on it.

# Architectural Diagram
![project-architecture](screens/00-architecture.png)

# Key Steps for Project
- Authentication
- Automated ML Experiment
- Deploy the best model
- Enable logging
- Swagger Documentation
- Consume model endpoints
- Create and publish a pipeline
- Documentation 

#### 1. AutoML Run -  Create an AutoML run and create upload bank marketing dataset to be used for training classification model.

![AutoML](screens/02 - Create Auto ML Run.png)

![image-1](screens/03 - Create Dataset.png)

![image-2](screens/04 - Dataset - 2.png)

![image-2](screens/05 - Dataset 3  - Upload from local.png)

![image-2](screens/06-Dataset Settings.png)

![image-2](screens/07- Dataset Created.png)

I created the compute to run the AutoML experiment.
![image-2](screens/08-AutoML Name and Create Compute.png)

![image-2](screens/09-Compute Cluster.png)

![image-2](screens/10-AuotML Configuration.png)

AutoML experiment is RUN once I pressed Finish.
![image-2](screens/11- AutoML Run.png)

![image-2](screens/12-Experiment is Running.png)

#### 2. AutoML gave the best model as Voting Ensemble with an accuracy of 91.98%. I Deployed this model by pressing the Deploy button.

![image](screens/13-Best Model.png)

![image](screens/14-Deploy.png)

Realtime endpoint is created.
![image](screens/15-Endpoint.py)

Next I enabled application insights by running the log file.
![image](screens/16-log file.png)

![image](screens/17-run logs.py file.png)

Model explainer is enables once the file is run.
![image](screens/17-run logs18-Model Explainer enabled.png)

![image](screens/19-logs file.png)

#### 3. Next I ran the swagger.sh and serve.py scripts to display the swagger documentation.
![image](screens/20- run swagger.png)

Check swagger is running.
![image](screens/21-check swagger is running.png)

![image](screens/22-run serve file.png)

#### 4. Consume Model Endpoint and Run benchmark.
By running the endpoint.py script and providing the data in correct format.

![image](screens/23- run endpoints file.png)

Run the apache benchmark to gauge the performance of endpoint.
![image](screens/24 - Run Benchmark.png)

#### 5. Run the Azure SDK pipeline to automate the training and deployment steps.
Create and submit a pipeline run with AutoML step using Azure SDK.
![image](screens/250-Create and submit pipeline.png)

We can see the pipeline run un Azure ML studio.
![image](screens/25-Pipeline Running in Azure ML studio.png)

![image](screens/26-Pipeline running.png)

![image](screens/29-pipeline running.png)

![image](screens/27-pipeline run finished.png)

Pipeline execution in run details widget.
![image](screens/28-run details.png)

![image](screens/30- pipeline run widget.png)

![image](screens/31-Dataset and AutoML.png)

Test the best model before publishing it.
![image](screens/251-test best model.png)


#### 5. Consume the best model with REST endpoint.

Next I published and created REST endpoint to consume the best model.
![image](screens/32 - Rest Endpoint.png)

![image](screens/33 - http request to endpoint.png)

![image](screens/34 - Pipeline rest endpint.png)

Rest endpoint is active.
![image](screens/35-Pipeline Runs.png)

![image](screens/36 - Pipeline Endpoint.png)

![image](screens/37- Pipeline rest endpint.png)

Endpoint is running and can be seen using RunDetails widget as well.
![image](screens/38- running.png)

# Standout Suggestions
1. Increase the AutoML executions time to allow Azure to find other algorithms with better accuracy.
2. Allow Deep Learning algorithms in AutoML step.
3. Explore edge deployment for endpoint.
