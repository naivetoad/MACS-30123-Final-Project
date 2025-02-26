# ArXiv Scholarly Article Analysis

This project focuses on extracting, processing, and analyzing a large dataset 
of scholarly articles from arXiv, leveraging big data technologies and machine 
learning models to uncover trends and categorize research fields.

## Data Extraction and Processing

The project begins with extracting data from an Amazon S3 bucket, which 
contains approximately 1.7 million scholarly articles in JSON format. The 
dataset is processed using Apache Spark on Amazon EMR clusters configured with 
eight r5.xlarge instances, each equipped with 4 vCores and 32 GiB of memory, 
ensuring efficient handling of large-scale data.

## [Exploratory Data Analysis](EDA.ipynb) (EDA)

An initial phase of Exploratory Data Analysis is conducted to understand the 
dataset’s structure and key statistical insights. 

Findings include:
1. Physics is the most published field, followed by Mathematics, Computer 
Science, and Astronomy.
2. Significant publication surges occurred in 2009, 2015, and 2023.
3. Computer Science grew from being the least studied field in 2007 to the most 
studied field in 2024.

## [Latent Dirichlet Allocation](LDA.ipynb) (LDA)

The project utilizes Latent Dirichlet Allocation to uncover latent topics 
within article abstracts. 

The process includes:
1. Preprocessing – Text normalization, punctuation removal, tokenization, and 
stopword filtering.
2. Vectorization – Converting text into numerical representations for analysis.
3. Topic Identification – Training the LDA model to extract underlying research 
themes.

LDA results confirm the growing prominence of Computer Science, surpassing 
Astronomy, Mathematics, and Physics as the dominant field from 2007 to 2024.

## [Multinomial Logistic Regression](MLR.ipynb) (MLR)

To classify articles into predefined research fields, a Multinomial Logistic 
Regression model is trained using abstract text. 

The pipeline includes:
1. Preprocessing – Tokenization, stopword removal, vectorization, and 
categorical label encoding.
2. Model Training – Training the MLR model to classify articles into research 
fields.
3. Evaluation – Performance assessment using accuracy and ROC AUC metrics.

The final model achieved a test accuracy of 0.86, effectively classifying 
research articles across disciplines.