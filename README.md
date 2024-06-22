# Arabic language hatespeech detection in YouTube comments and Twitter posts using Spark, NLP, and Docker.
[nlpport.pptx](https://github.com/user-attachments/files/15938385/nlpport.pptx)

## Project Overview
This project aims to detect hate speech in a large dataset of Arabic text data gathered from YouTube and Twitter, using Natural Language Processing (NLP) techniques and Apache Spark on a docker container for reproducible big data processing. The project utilizes a versatile skill set, including data preprocessing, machine learning, and data visualization, to build an effective hate speech detection model. This project assumes new records to be streamed into the trained model.


## Table of Contents
- [Introduction](#introduction)
- [Workflow](#workflow)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Tools and Libraries](#tools-and-libraries)
- [Results](#results)


## Introduction
Hate speech detection is a crucial task in moderating online content to create a safer digital environment. This project leverages Apache Spark for handling large volumes of data efficiently and employs NLP techniques to preprocess and analyze text data for hate speech classification.

## Workflow
Six experiments were performed on the SVM, NB, LR and Random Forest models to find the best pipeline for processing production stream data. The common steps between the pipelines are tokenizer, stopwords removal, TF-IDF, and string indexer. 

The pipelines differ in using lemmatizer and n-grams, where we have the following.
- Pipeline1: using common steps and lemmatizer without n-grams
- Pipeline2: using common steps without both lemmatizer and n-grams
- Pipeline3: using common steps with lemmatizer and n-gram=2
- Pipeline4: using common steps without lemmatizer and n-gram=2
- Pipeline5: using common steps without lemmatizer and n-gram=3
- Pipeline6: using common steps with lemmatizer and n-gram=3

![image](https://github.com/mohammad-awad-ds/Natural-Language-Processing-NLP/assets/64756947/9e88b966-07b4-4d78-a21c-497bdee84f3e)


## Dataset
The private dataset used in this project consists of text data labeled for hate speech with a total of 23,282 records. Each record represents a comment or a post, with 4821 records labeled as hatespeech and 18461 labeled as not hatespeech. To overcome the imbalance in dataset, the undersampling technique of the majority class is used to create a balanced dataset. The data is preprocessed further to remove noise and irrelevant information, making it suitable for training machine learning models.


## Installation
To run this project, you need to have Docker installed.

### Steps to Install
1. Clone the repository:
   ```bash
   git clone https://github.com/mohammad-awad-ds/HateSpeechDetection.git
   cd HateSpeechDetection
   ```
2. Start the Docker containers:
   ```bash
   docker-compose up
   ```

## Usage
To use this project, follow these steps:
1. Open JupyterLab by navigating to `http://localhost:8888` in your web browser.
2. Open the `notebooks/` directory and run the notebook `NLP_BigData_HateSpeechDetection_Project.ipynb`.

The notebook includes steps for data loading, preprocessing, feature extraction, model training, and evaluation. 

## Tools and Libraries
The following tools and libraries are used in this project:
- **JupyterLab**: `andreper/jupyterlab:3.0.0-spark-3.0.0`
- **Apache Spark**: `andreper/spark-master:3.0.0`, `andreper/spark-worker:3.0.0`
- **PySpark**: Python API for Spark
- **Spark NLP**: Library for Natural Language Processing on Apache Spark
- **Python Libraries**: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `NLTK`, and others

## Results
The results of the hate speech detection model, including performance metrics such as accuracy, precision, recall, and F1-score, are documented in the notebook. Visualizations of the data distribution and model performance are also included.

In conclusion, the SVM model performed the best for the first two pipelines, and it was less sensitive to the existence of lemmatization. As the n-gram value increased, the classifiers generally started to drop in their results, except for the Random Forest model, which was the best classifier for the higher n-grams pipelines and was less sensitive to change in n-gram value.
![image](https://github.com/mohammad-awad-ds/Natural-Language-Processing-NLP/assets/64756947/ced8d1d3-7cd2-4a13-8862-7aa44538a9bc)




