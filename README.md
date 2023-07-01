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