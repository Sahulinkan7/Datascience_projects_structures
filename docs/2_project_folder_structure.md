### 2.1 Project folder structure creation

Step 1 : create a python file named "template.py" in your project directory and paste below code into it.
        
```python

    import os
    from pathlib import Path 
    import logging

    logging.basicConfig(level=logging.INFO,format='[%(asctime)s: %(message)s]')

    project_name = "project_src_folder_name"  ## change as per your project name

    list_of_files=[
        f"{project_name}/__init__.py",
        f"{project_name}/entity/__init__.py",
        f"{project_name}/entity/config_entity.py",
        f"{project_name}/entity/artifact_entity.py",
        f"{project_name}/components/__init__.py",
        f"{project_name}/components/data_ingestion.py",
        f"{project_name}/components/data_validation.py",
        f"{project_name}/components/data_transformation.py",
        f"{project_name}/components/model_trainer.py",
        f"{project_name}/components/model_evaluation.py",
        f"{project_name}/components/model_pusher.py",
        f"{project_name}/configuration/__init__.py",
        f"{project_name}/constants/__init__.py",
        f"{project_name}/logger/__init__.py",
        f"{project_name}/exception/__init__.py",
        f"{project_name}/pipeline/__init__.py",
        f"{project_name}/pipeline/tain_pipeline.py",
        f"{project_name}/pipeline/prediction_pipeline.py",
        f"{project_name}/utils/__init__.py",
        f"{project_name}/utils/commonutils.py",
        f"config/config.yaml",
        f"params.yaml",
        f"notebooks/experiments.ipynb",
        "app.py",
        "train.py",
        "requirements.txt",
        "Dockerfile",
        ".dockerignore",
        "setup.py"
        ]   

    for file_path in list_of_files:

        filepath=Path(file_path)
        filedir,filename=os.path.split(filepath)

        if filedir!="":
            os.makedirs(filedir,exist_ok=True)
            logging.info(f"creating file directory {filedir} for file {filename}")
            
        if not (os.path.exists(filepath)) or (os.path.getsize(filepath)==0):
            with open(filepath,"w") as file:
                pass
                logging.info(f"Empty file {filepath} created successfully !")
        else:
            logging.info(f"file {filepath} already exist.")

```
Note : modify template.py file as per your requirements. 

Step 2 : Run the "template.py" script file from terminal . It will create the basic folder structure for the project.

```python
    python template.py
```
### 2.2 Installing libraries in Virtual Environment

To install libraries in virtual environment , must activate the virtual environemnt first.

for command prompt and powershell terminal

```python
conda activate virtual_env_path/
```

for git bash or linux based terminal 

```python
source activate virtual_env_path/
```

Now add required libraries name and its version in "requirements.txt" file and run below command.

```python
pip install -r requirements.txt
```

This above command will read the requirements from "requirements.txt" file and install all packages in virtual environment.
