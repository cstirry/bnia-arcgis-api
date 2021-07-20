# Explore BNIA data using the ArcGIS API in a Jupyter Notebook

The included notebook explores [BNIA data](https://bniajfi.org) with various visualization libraries.

If you are interested in using this setup for your own analysis, the following instructions walk through forking your
own repository for your own BNIA data exploration in a notebook,
and how to create a python environment with the necessary packages.

## Get repository and create a private forked repository for own exploration

Pull this repository to your local machine:

```
git clone URL
```

* Login to your github and create a private repo : YOUR_REPO.

* Get this repo <br> ``git clone --bare URL``

* Mirror this to your private repo <br>
```
cd {name}.git
git push --mirror YOUR_REPO
```

* You can now delete the initial directory cloned two steps ago.

* Clone your private repo on your local system<br> ``git clone YOUR_REPO``

* Next <br>
```
cd YOUR_REPO
git remote add upstream URL
```
Check if the remote branch has been added using ``git remote -v``

* Now you can use it like this <br>
```
git pull upstream master # the original repo 
git push origin master # your repo 
```
If you do not specify the remote, it will default to the origin (your repo)

* If you want, you can disable pushing to upstream using<br> ``git remote set-url --push upstream PUSH_DISABLED``

## Environment

Environments are used to keep different python versions and packages isolated from each other, generally each project/application will have an independent python environment. For example, we will be using Python 3.7 and packages like numpy, networkx etc, and we want them to be isolated from any other python projects you might have. 
Make sure you have Conda downloaded [Miniconda](https://docs.conda.io/en/latest/miniconda.html) and installed locally. Conda is an open source package and environment management system.

To create a new environment run:

```
conda create --name your_env python=3.7 -y
```

Once it's created you can activate it by running:

```
conda activate your_env
```

The environment is not attached to any specific folder so you can navigate to different directories while it remains activated.
If you want to change the environment you can deactivate it using `conda deactivate` and then activate another one.
To see the list of all environments you have on your machine, run `conda env list`.

## Python Packages

Python packages used in the initial exploration. You may want to update the requirements list to add your own.

* **jupyter** - interactive notebook
* **arcgis** - the arcgis python api package
* **numpy** - a package for scientific computing
* **pandas** - a package for data analysis
* **matplotlib** - a plotting library

You can see the complete list of packages and required versions in [./requirements.txt](./requirements.txt).

Within your directory, activate your environment (`conda activate your_env`), then run:

```
pip install -r requirements.txt
```

Once installed, you can run `pip freeze` to see the list of all of the packages installed in the environment.

The ArcGIS Python API has various sample notebooks that could be useful to [explore](https://github.com/Esri/arcgis-python-api)

## Jupyter

Assuming, you have installed jupyter. To open it up you can run in your terminal:

```
jupyter notebook
```

It will start a python kernel which you can access via [https://localhost:8888](https://localhost:8888/) in your browser,
where you can open `notebook.ipynb`.