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