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

![AutoML](screens/02.png)

![image-1](screens/03.png)

![image-2](screens/04.png)

![image-2](screens/05.png)

![image-2](screens/06.png)

![image-2](screens/07.png)

I created the compute to run the AutoML experiment.
![image-2](screens/08.png)

![image-2](screens/09.png)

![image-2](screens/10.png)

AutoML experiment is RUN once I pressed Finish.
![image-2](screens/11.png)

![image-2](screens/12.png)

#### 2. AutoML gave the best model as Voting Ensemble with an accuracy of 91.98%. I Deployed this model by pressing the Deploy button.

![image](screens/13.png)

![image](screens/14.png)

Realtime endpoint is created.
![image](screens/15.py)

Next I enabled application insights by running the log file.
![image](screens/16.png)

![image](screens/17.py file.png)

Model explainer is enables once the file is run.
![image](screens/18.png)

![image](screens/19.png)

#### 3. Next I ran the swagger.sh and serve.py scripts to display the swagger documentation.
![image](screens/20.png)

Check swagger is running.
![image](screens/21.png)

![image](screens/22.png)

#### 4. Consume Model Endpoint and Run benchmark.
By running the endpoint.py script and providing the data in correct format.

![image](screens/23.png)

Run the apache benchmark to gauge the performance of endpoint.
![image](screens/24.png)

#### 5. Run the Azure SDK pipeline to automate the training and deployment steps.
Create and submit a pipeline run with AutoML step using Azure SDK.
![image](screens/250.png)

We can see the pipeline run un Azure ML studio.
![image](screens/25.png)

![image](screens/26.png)

![image](screens/29.png)

![image](screens/27.png)

Pipeline execution in run details widget.
![image](screens/28.png)

![image](screens/30.png)

![image](screens/31.png)

Test the best model before publishing it.
![image](screens/251.png)


#### 5. Consume the best model with REST endpoint.

Next I published and created REST endpoint to consume the best model.
![image](screens/32.png)

![image](screens/33.png)

![image](screens/34.png)

Rest endpoint is active.
![image](screens/35.png)

![image](screens/36.png)

![image](screens/37.png)

Endpoint is running and can be seen using RunDetails widget as well.
![image](screens/38.png)

# Standout Suggestions
1. Increase the AutoML executions time to allow Azure to find other algorithms with better accuracy.
2. Allow Deep Learning algorithms in AutoML step.
3. Explore edge deployment for endpoint.
