# End-To-End-NLP-Project

## Steps

* create and activate the environment
```bash
conda create -n txt-env python=3.8 -y
conda activate txt-env
```

* create template.py to define the project folder structure
```bash
touch template.py
python template.py
```

* define a setup.py file 

* add required libraries to requirements.txt and install it
```bash
pip install -r requirements.txt
pip freeze
pip freeze | grep pandas
```

* define logging file 

**Note:** The Logging is a means of tracking events that happen when some software runs.

* define utils/common.py

**Note:** The utils/common.py makes it easy to execute common tasks in Python scripts

* run a notebook in google colab for experiment purpose and download it to "research/" dir


```bash
Workflows
 1. Update config.yaml
 2. Update params.yaml
 3. Update entity
 4. Update the configuration manager in src config
 5. update the components
 6. update the pipeline
 7. update the main.py

```

####################**Data Ingestion**##########################

**Note:** **Data ingestion** is the process of importing large, assorted data files from multiple sources into a single, cloud-based storage medium.

* define config/config.yaml --> define constants/__init__.py --> and create 01_data_ingestion.ipynb and run it

* define entity/__init__.py --> define /config/configuration.py --> define components/data_ingestion.py --> define pipeline --> and main.py


####################**Data Validation**##########################

**Note:** **Data validation** is the process of ensuring data has undergone data cleansing to confirm they have data quality, that is, that they are both correct and useful.

* define config/config.yaml --> and create 02_data_validation.ipynb and run it

* define entity/__init__.py --> define /config/configuration.py --> define components/data_validation.py --> define pipeline --> define and run main.py

####################**Data Transformation**##########################

**Note:** **Data transformation** means taking data stored in one format and converting it to another

* define config/config.yaml --> and create 03_data_transformation.ipynb and run it

* define entity/__init__.py --> define /config/configuration.py --> define components/data_transformation.py --> define pipeline --> define and run main.py

####################**Model Training**##########################


* define config/config.yaml --> define params.yaml --> and create 04_model_training.ipynb and run it

* define entity/__init__.py --> define /config/configuration.py --> define components/model_training.py --> define pipeline --> define and run main.py



####################**Model Evaluation**##########################


* define config/config.yaml --> and create 05_model_evaluation.ipynb and run it

* define entity/__init__.py --> define /config/configuration.py --> define components/model_evaluation.py --> define pipeline --> define and run main.py


####################**Prediction and UI**#########################

* create src/textSummarizer/pipeline/prediction.py
* create app.py


###################**Dockerfile and cicd Section**################

* create Dockerfile
```bash
FROM python:3.8-slim-buster

RUN apt update -y && apt install awscli -y
WORKDIR /app

COPY . /app

RUN pip install -r requirements.txt
RUN pip install --upgrade accelerate
RUN pip uninstall -y transformers accelerate
RUN pip install transformers accelerate

CMD ["python3", "app.py"]

```

* create .github/workflows/cicd.yaml


******************************************************************************************************

###############**AWS Section**################

**Note:** we will deploy AWS-CICD using Github-Actions

### 1. Login to AWS console
### 2. Create IAM user for deployment and download the project_accessKeys
```bash
#with specific access

1. ECR: Elastic Container registry to save your docker image in aws
2. EC2 access : It is virtual machine


#Description: About the deployment

1. Build docker image of the source code

2. Push your docker image to ECR

3. Launch Your EC2 

4. Pull Your image from ECR in EC2

5. Lauch your docker image in EC2

#Policy for IAM:

1. AmazonEC2ContainerRegistryFullAccess
2. AmazonEC2FullAccess
```

### 3. Create ECR repo to store/save docker image
```bash
- Save the URI: 060145207853.dkr.ecr.ap-south-1.amazonaws.com/textSummarizer
```

### 4. Create EC2 machine (Ubuntu)
### 5. Open EC2 and Install docker in EC2 Machine:
```bash
#optinal

sudo apt-get update

sudo apt-get upgrade -y

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

### 6. Configure EC2 as self-hosted runner:

```bash
setting-->actions-->runner-->new self hosted runner--> choose os--> copy each command and run it on EC2 Instance Connect
```
### 7. Setup github secrets:
```bash
AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = ap-south-1

AWS_ECR_LOGIN_URI = demo>>  060145207853.dkr.ecr.ap-south-1.amazonaws.com

ECR_REPOSITORY_NAME = textSummarizer
```
******************************************************************************************************