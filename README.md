# Arabic language hatespeech detection in YouTube comments and Twitter posts using Spark, NLP, and Docker.

## Project Overview
This project aims to detect hate speech in a large dataset of Arabic text data gathered from YouTube and Twitter, using Natural Language Processing (NLP) techniques and Apache Spark on a docker container for reproducible big data processing. The project utilizes a versatile skill set, including data preprocessing, machine learning, and data visualization, to build an effective hate speech detection model.


## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Tools and Libraries](#tools-and-libraries)
- [Results](#results)


## Introduction
Hate speech detection is a crucial task in moderating online content to create a safer digital environment. This project leverages Apache Spark for handling large volumes of data efficiently and employs NLP techniques to preprocess and analyze text data for hate speech classification.

## Dataset
The private dataset used in this project consists of text data labeled for hate speech. The data is preprocessed to remove noise and irrelevant information, making it suitable for training machine learning models.


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

