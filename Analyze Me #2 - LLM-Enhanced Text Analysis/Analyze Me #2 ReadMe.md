# Analyze Me #2: LLM-Enhanced Text Analysis

## Overview

`Analyze_Me_2.ipynb` investigates whether the language in a job posting can predict if it is fraudulent and which terms most influence the predictions. Despite the folder's LLM-enhanced title, the notebook's implemented approach is traditional machine learning: TF-IDF text features and a class-weighted logistic regression model.

## What it does

1. Loads and explores a dataset of real and fraudulent job postings.
2. Checks data types, missing values, blank strings, and duplicate rows.
3. Combines each posting's title, company profile, description, requirements, and benefits into one text field.
4. Cleans the text by lowercasing, removing URLs, HTML, punctuation, and English stopwords.
5. Splits the data into stratified training and test sets, then converts text to TF-IDF features using unigrams and bigrams.
6. Trains and evaluates a class-weighted logistic regression model.
7. Visualizes model performance and the words most associated with fraudulent versus real postings.

## Data

The notebook loads `fake_job_postings.csv` from the Kaggle dataset `shivamb/real-or-fake-fake-jobposting-prediction` using `kagglehub`. The dataset has 17,880 job postings and 18 fields, including posting text and a `fraudulent` target label. The notebook downloads or accesses the dataset through KaggleHub; the CSV is not included in this folder.

## How to run

1. Open `Analyze_Me_2.ipynb` in Jupyter or Google Colab.
2. Use a Python environment with `kagglehub`, pandas, NumPy, Matplotlib, Seaborn, NLTK, and scikit-learn installed.
3. Configure Kaggle access if prompted so KaggleHub can retrieve the dataset.
4. Run the notebook from top to bottom. It downloads NLTK's English stopword list and retrieves the dataset on first use.
5. Review the classification report, precision-recall AUC, confusion matrix, and word-weight visualizations.

## Key findings

- The dataset is highly imbalanced: 17,014 real postings (95.16%) and 866 fraudulent postings (4.84%).
- On the stratified test set, the model achieved 97% overall accuracy and 0.8874 PR-AUC. For fraudulent postings, precision was 0.64 and recall was 0.90.
- The high recall means the model identified most fraudulent postings in this test set, while its lower precision means some real postings were also flagged.
- Among the top fraud-associated terms, phrases such as `data entry`, `work home`, and `oil gas` appeared in postings with higher observed fraud rates. These are associations in this dataset, not proof that any individual posting containing these words is fraudulent.

## Limitations

- Fraudulent postings are rare, so accuracy alone can be misleading; class-specific precision, recall, and PR-AUC are more informative.
- The class-weighted model favors detecting the minority fraud class, which can increase false positives.
- TF-IDF and logistic regression capture word and phrase associations, not deeper context or intent. This notebook does not implement a large language model.
- Top coefficient terms are model associations, not causal explanations or reliable standalone fraud indicators.
- Results depend on this dataset, the train/test split, text cleaning choices, and model settings; the model should not be used as the sole basis for employment or moderation decisions.

## Tools

Python, Jupyter/Google Colab, KaggleHub, pandas, NumPy, Matplotlib, Seaborn, NLTK, scikit-learn, TF-IDF, and logistic regression.
