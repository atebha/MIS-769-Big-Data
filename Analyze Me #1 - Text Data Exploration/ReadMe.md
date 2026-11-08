# Analyze Me #1: Text Data Exploration

## Overview

`Text_Me_1.ipynb` explores a college-major return-on-investment dataset to investigate the question: **Does the institution you attend matter more for earnings than the major you choose?** The notebook combines exploratory data analysis, visual comparisons, and regression models to compare the relationship between major, institution tier, and estimated 10-year added earnings.

## What it does

1. Loads the college-major ROI CSV into a pandas DataFrame and inspects sample records, dimensions, data types, and categories.
2. Checks for missing values and selects eight fields for the analysis.
3. Compares 10-year added earnings by institution tier, major category, and individual major using means, medians, and distributions.
4. Examines net college costs and the mix of majors across institution tiers.
5. Fits OLS regression models using major, institution tier, their combination, and their interaction to compare explanatory power.
6. Repeats the model comparison using log-transformed added earnings and visualizes estimated differences.

## Data

The notebook uses `college_major_roi.csv`, sourced from Kaggle's [College Major ROI dataset](https://www.kaggle.com/datasets/sergionefedov/college-major-roi). The file contains 30,000 graduate records and 18 columns, including major, institution tier, region, net cost, estimated earnings, and ROI measures.

The notebook reads the CSV by filename, so keep it in the same working directory as the notebook when running locally. A copy of the dataset is included in this folder.

## How to run

1. Open `Text_Me_1.ipynb` in Jupyter or Google Colab.
2. Ensure `college_major_roi.csv` is available in the notebook's working directory.
3. Use a Python environment with pandas, NumPy, Matplotlib, and statsmodels installed.
4. Run the cells from top to bottom to load the data, produce the analysis, fit the models, and render the plots.

## Key findings

- Major alone explains about 54.8% of the variation in 10-year added earnings in the notebook's raw-earnings OLS model; institution tier alone explains about 6.1%.
- Including both major and institution tier raises model R² to about 60.8%. An interaction model raises it to about 63.2%.
- The notebook's log-earnings comparison attributes substantially more unique explanatory power to major than to institution tier (about 0.768 versus 0.047 in the reported variance decomposition).
- These results suggest major is more strongly associated with added earnings than institution tier in this dataset, while institution tier still contributes information.

## Limitations

- The regression models describe associations in this dataset; they do not establish that changing majors or institutions causes a particular earnings outcome.
- The model comparisons use a limited set of predictors. Other factors that may relate to earnings are not controlled for in the final analysis.
- Earnings distributions can be skewed, so raw-dollar and log-transformed models may tell different stories. Interpret the model results and plots in context.
- The findings are specific to this dataset and its definitions of earnings, ROI, and institution tiers; they should not be treated as guarantees for an individual student's outcome.

## Tools

Python, Jupyter/Google Colab, pandas, NumPy, Matplotlib, statsmodels, and the College Major ROI CSV dataset.
