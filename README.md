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