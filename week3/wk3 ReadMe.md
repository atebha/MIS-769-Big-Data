# Week 3: Text Processing with spaCy and NLTK

## Overview

[HW03.ipynb](./HW03.ipynb) is a hands-on lab on cleaning and analyzing text. It
demonstrates how stopword choices affect meaning and sentiment, and how to adapt
a cleaning pipeline to a specific domain.

## Notebook contents

The notebook walks through:

- Setting up spaCy and NLTK and loading review data
- Applying standard English stopwords and measuring what gets removed
- Building and justifying a domain-specific stopword list
- Preserving negation words so phrases such as “not good” retain their meaning
- Comparing original and cleaned text with word counts and word clouds
- Repeating the analysis with text from a domain of your choice

## Data

The example uses the training split of the Yelp Review Full dataset, limited to
20,000 reviews. Its labels represent star ratings from 1 to 5 (stored as 0 to 4
in the dataset). The notebook’s Domain Playground section is intended for
repeating the analysis with another text dataset.

## How to run

1. Open [HW03.ipynb](./HW03.ipynb) in Google Colab or another Jupyter
   environment.
2. Run the cells from top to bottom. The setup cell installs the required
   packages and downloads the spaCy English model and NLTK stopwords.
3. Complete the Domain Playground with your own text data, then rerun the
   relevant analysis and visualization cells.
4. Add your responses to the notebook’s debrief questions and save the
   completed notebook with its outputs.

The notebook uses `datasets` to load Yelp data and also uses pandas, spaCy,
NLTK, matplotlib, and WordCloud. Running the setup and data-loading cells
requires an internet connection.

## Key takeaways

- Generic stopword lists can remove useful information, especially negations
  that matter for sentiment.
- Domain-specific stopwords should be selected with a clear rationale; common
  words are not automatically meaningless.
- Compare results before and after cleaning rather than assuming a cleaning
  step improves the analysis.

## Limitations

The example is based on a bounded sample of Yelp reviews, so its vocabulary and
stopword choices may not generalize to other datasets or domains. Word clouds
are a visual summary of frequent words, not a substitute for contextual or
statistical analysis. The notebook’s basic negation checks may also miss
phrasing such as double negatives or less common forms of negation.
