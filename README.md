# Project Summary
This project will showcase a simple analysis of a dataset using PySpark and PyArrow. Although PySpark and PyArrow are better suited in a data pipeline and truly shine in a cluster setup, I simply want to get a first glance into these frameworks and the features they offer!

The notebook will have the following steps:
1. Open the data in PySpark
2. Explore the data
3. Clean up the data (if necessary)
4. Perform analysis on the data
5. Store the data in a persistent manner

# Dataset
The dataset taken from Kaggle is the [Brewery Operations and Market Analysis Dataset](https://www.kaggle.com/datasets/ankurnapa/brewery-operations-and-market-analysis-dataset/). This is a synthetically produced dataset of beer brewing conditions, sales trends and quality metrics of craft beer from the years 2020-2024.

# Setup Guideline


# 1. Open the data in PySpark
First notes: I tried running PySpark within a conda virtual environment, but after much trial and error I simply couldn't figure out how to link my JAVA installation with PySpark. I managed to get it working with a Python native environment (venv) and this is how we will move forward for the rest of the project.

We download the brewery dataset directly from Kaggle, for this you need to have a Kaggle account and API keys from Kaggle. If you want you can also download the dataset manually from Kaggle and reference the data_path manually.

We instantiate a PySpark session called "Brewery Data" and enable Arrow-based columnar data transfers. We then read in the brewery dataset into the PySpark session. 

Enabling Arrow (PyArrow in this case) is not mandatory and possibly unnecessary for a small dataset of 2GB, but there are also some benefits which are listed below:
- Efficient data transfer (e.g., if needed, will make the conversion between PySpark to Pandas more efficient)
- Improved performance (columnar memory format is a significantly faster method of processing data and reduces memory overhead)

Enabling Arrow in my case probably has little benefits, but at least no disadvantages!

# 2. Explore the data


