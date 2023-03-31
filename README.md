# ds-project-template

Template for creating ds simple projects

## Requirements

- pyenv
- python==3.9.8


### External Data
You will need a GeoJSON file with the shapes of the different ZIP code areas in King County for this notebook to work.
 
A GeoJSON file can be found on the official [Open Data portal of Seattle](https://data-seattlecitygis.opendata.arcgis.com/datasets/SeattleCityGIS::zip-codes/explore?location=47.496805%2C-121.972750%2C9.58).

Use a simplyfier service like [Mapshaper](https://mapshaper.org/) to reduce file size and complexity. Otherwise the Jupyter notebook could crash when it comes to plotting maps.

Define the path to your file in the second code block of the notebook:

    with open('data/kc_zipcode_geo.json') as gj:
        zip_geojson = json.load(gj)

## Setup

One of the first steps when starting any data science project is to create a virtual environment. For this project you have to create this environment from scratch yourself. However, you should be already familiar with the commands you will need to do so. The general workflow consists of... 

* setting the python version locally to 3.9.8
* creating a virtual environment using the `venv` module
* activating your newly created environment 
* upgrading `pip` (This step is not absolutely necessary, but will save you trouble when installing some packages.)
* installing the required packages via `pip`

At the end, you want to make sure that people who are interested in your project can create an identical environment on their own computer in order to be able to run your code without running into errors. Therefore you can create a `requirements file` and add it to your repository. You can create such a file by running the following command: 

```bash
pip freeze > requirements.txt
```

*Note: In rare case such a requirements file created with `pip freeze` might not ensure that another (especially M1 chip) user can install and execute it properly. This can happen if libraries need to be compiled (e.g. SciPy). Then it also depends on environment variables and the actual system libraries.*



### Environment

This repo contains a requirements.txt file with a list of all the packages and dependencies you will need. 


In order to install the environment you can use the following commands:

```
pyenv local 3.9.8
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```