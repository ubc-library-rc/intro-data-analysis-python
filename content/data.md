---
layout: default
title: Working with Dataset
nav_order: 7
parent: Workshop Content
has_toc: false
---

## 1. Working with Data Frames through Pandas

Data frames is a two-dimensional, tabular data structure resembling a spreadsheet or SQL table, where data is organized into rows and columns. Each column can contain data of the same or different data types, such as numbers, strings, or dates. The [pandas](https://pandas.pydata.org/docs/index.html) library provides a powerful implementation of data frames, making it widely used for handling structured data,  allowing you to efficiently store, filter, transform, and analyze large datasets.

<p align="center">
<img src="https://pandas.pydata.org/docs/_images/01_table_dataframe.svg" width="300" />
</p>
*Source: Pandas, [Intro to pandas: What kind of data does pandas handle?](https://pandas.pydata.org/docs/getting_started/index.html#intro-to-pandas)*


### Practice 3
Go to your Google Colab notebook, insert new cells and try to download the 2016 and 2021 Census data about the race and gender of judges in Canada [https://abacus.library.ubc.ca/dataset.xhtml?persistentId=hdl:11272.1/AB2/PG2NB4](https://abacus.library.ubc.ca/dataset.xhtml?persistentId=hdl:11272.1/AB2/PG2NB4). The dataset is retrieved from [Abacus](https://abacus.library.ubc.ca/).

Input
{: .label .label-green}
```python
# download the data
import requests
download_url = "https://abacus.library.ubc.ca/api/access/datafile/:persistentId?persistentId=hdl:11272.1/AB2/PG2NB4/BRXJ1Z"
target_csv_path = "judge.csv"
response = requests.get(download_url)
response.raise_for_status()    # Check that the request was successful
with open(target_csv_path, "wb") as f:
    f.write(response.content)
print("Download ready.")
```

Input
{: .label .label-green}
```python
# read in the data 
import pandas as pd
judge = pd.read_csv("judge.csv")

# basic info
print(type(judge))
print(len(judge))
print(judge.shape)
judge.info()
judge.describe()
```

## 2. Libraries at Different Stages

Data analysis procedure can be divided into the following stages:
<p align="center">
<img src="https://r4ds.hadley.nz/diagrams/data-science/whole-game.png" width="600" />
</p>
*Source: Hadley Wickham, Mine Çetinkaya-Rundel, & Garret Frolemund, [R for Data Science (2e)](https://r4ds.hadley.nz/whole-game.html)*

<br>
Some commonly used Python libraries at different stages of data analysis include:

| Stage                   | Python Libraries                         | R Packages (as comparison if you are familiar with R)                 |
|-------------------------|------------------------------------------|--------------------------|
| Data Import             | `pandas`, `numpy`, `json`                | `readr`, `haven`, `readxl`, `jsonlite` |
| Tidying & Transformation| `pandas`, `regex`                        | `dplyr`, `tidyr`, `stringr`, `forcats` |
| Data Visualization      | `matplotlib`, `seaborn`                  | `ggplot2`, `gganimate`               |
| Modeling                | `scikit-learn`, `statsmodels`, `xgboost`, `keras`/`tensorflow`, `pytorch` | `caret`, `randomForest`, `glmnet`, `xgboost`, `nnet` |
| Communication           | `jupyter`, `pandas-profiling`, `markdown`, `nbconvert` | `knitr`, `rmarkdown`                   |

_Note. This table is not exhaustive and represents commonly used packages/libraries in R and Python for data analysis. Depending on the specific use case and requirements, additional packages/libraries might be utilized._

<br>
<p style="color:grey; font-size:14px; padding-top: 2em">
This page is meant to let you take a stab at working with data frame in Python.<br>
What questions do you have? Now is a good time  to share your questions, thoughts and comments.