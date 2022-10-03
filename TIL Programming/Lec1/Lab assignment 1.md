[<img src="https://raw.githubusercontent.com/mbakker7/exploratory_computing_with_python/master/tudelft_logo.png" width="200" align='right'>](https://www.tudelft.nl/citg/over-faculteit/afdelingen/geoscience-remote-sensing/staff/scientific-staff/dr-stef-lhermitte)


# Python Environment Assignment 
*Created by Panchamy Krishnakumari (p.k.krishnakumari at tudelft.nl)*

In this course you will use several libraries that you need to install and are listed below. The setup for installing these packages in your local computer conda distribution is included in brightspace as well as below. 

*In case of technical installation problems, the cloud-based Google Colab online jupyter notebooks is an alternative. But, we highly recommend setting up your own local environment and working with visual studio code as this makes collaboration easier.*

# Introduction

## Required packages for the courses

The packages used in this course are:

- [copy](https://docs.python.org/3/library/copy.html): a Python package to make shallow and deep copy of Python objects.
- [random](https://docs.python.org/3/library/random.html): a Python package for random number generation
- [datetime](https://docs.python.org/3/library/datetime.html): a Python package to manipulate dates and times
- [math](https://docs.python.org/3/library/math.html): a Python package for mathematical functions

- [numpy](https://numpy.org): a Python package for scientific computing
- [json](https://docs.python.org/3/library/json.html): a Python package to encode and decode JSON format
- [pandas](https://pandas.pydata.org): a Python package for data analysis and manipulation
- [geopandas](https://geopandas.org/en/stable/): a Python package to make working with geospatial data in python easier. GeoPandas extends the datatypes used by pandas to allow spatial operations on geometric types.

- [matplotlib](https://matplotlib.org): a Python package for creating static, animated and interactive visualisations
- [seaborn](https://seaborn.pydata.org): a Python package for statistical data visualisation
- [plotly.express](https://plotly.com/python/plotly-express/): a Python package for interactive charts and maps. Plotly Express is a built-in part of the plotly library.
- [folium](http://python-visualization.github.io/folium/): a Python package for visualising and maniplating geospatial data.

- [scipy](https://scipy.org): a Python package for fundamental algorithms for scientific computing
- [scikit-learn](https://scikit-learn.org/stable/): a Python package for general machine learning algorithms and predictive data analysis

## Setting up your own python environment

To install the packages on your local computer, follow the instructions below:

- For windows, first launch your conda prompt. If you don't know how to launch the conda prompt in Windows check [here](https://docs.anaconda.com/anaconda/install/verify-install/#conda). Once the conda prompt is launched, you should run the following commands in this prompt:

- For Mac/Linux you should open your terminal and the you can directly run the following commands in the terminal:

`conda create --name TIL6022`

This line is to create a new conda environment with name TIL6022. Subsequently, you need to active that newly created environment:

`conda activate TIL6022`

Within this newly created environment, you can first install necessary libraries:

`conda install --force-reinstall -y -q --name TIL6022 -c conda-forge --file requirements.txt`

Once you succeeded in installing these packages, you can run the notebook in TIL6022 environment. In VS code, the environment will appear automatically and you can switch your workarea to that specific environment.

Once this is done, these packages can be imported as normal packages and you should be able to run the code in the rest of this notebook without major errors. If this is the case you are fine to start the course.


## The Zen of Python


```python
import this
```

    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
    

# Part I - Verifying the installation


```python
import copy
import random
import datetime
import math
import numpy
import json
import pandas
import geopandas
import matplotlib.pyplot as plt
import seaborn
import plotly.express
import folium #folium needs conda-forge
import scipy
import sklearn

print('All libraries are installed correctly')
```

    All libraries are installed correctly
    

# Part II - Markdown Assignments

Look at *Expected output.pdf* to see what needs to be created. You can find helpers for markdown [here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## Q1: Create a nested list

### Answer 1
  1. Part II - Markdown Assignments
      - Q1: Create a nested list   
          – Answer 1  
      - Q2: Quoting code  
          – Answer 2  
      - Q3: Add the sample figure  
          – Answer 3

## Q2: Quoting code

### Answer 2
The following is a piece of code in python:
```
import math
print(math.sqrt(100))
```

## Q3: Add the sample picture

### Answer 3
Time for some sun!  
![This is an image](https://brightspace.tudelft.nl/content/enforced/501308-TIL6022+2022+1/sample_picture.jpg?d2lSessionVal=07j6UjV7CMvKFSdFssR6VqN6P&ou=501308)

## BONUS: Add a task list


- [x] Completed Q1
- [x] Completed Q2
- [x] Completed Q3
- [ ] Completed Bonus

# Submission
If all cells work without problems, you are ready to start the notebook sessions in the quarter. 

Run all the cells and download the notebook as a pdf and submit this pdf in the assignment 
