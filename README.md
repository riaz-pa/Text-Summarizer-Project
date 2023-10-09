# Text Summarizer Project

<p align="center">
  <img src="https://github.com/riaz-pa/Datasets/blob/main/read.png" alt="Project Image" width="300" height="200">
</p>

## Overview
The Text Summarizer Project is a natural language processing (NLP) application designed to automatically generate concise and coherent summaries from longer texts or documents. Its primary purpose is to assist users in quickly extracting essential information from large volumes of textual data.

## Key Features
- Text summarization using state-of-the-art models such as Pegasus and BART.
- Customizable configuration for various summarization tasks.
- Workflow automation for data transformation, model training, and evaluation.
- Compatibility with different datasets and text sources.
- Easy-to-use command-line interface (CLI) and graphical user interface (GUI).
- Integration of pre-trained models for faster summarization.

## Project Goals
1. Enable users to summarize lengthy articles, documents, or news articles effectively.
2. Facilitate research and development in NLP and summarization techniques.
3. Provide an open-source, customizable solution for text summarization tasks.
4. Offer a user-friendly interface for summarization tasks, even for non-technical users.

The Text Summarizer Project aims to simplify the process of digesting large amounts of text by providing accurate and coherent summaries, ultimately saving time and improving information retrieval efficiency.

## Table of Contents

- [Workflow](#workflow)
- [Directory Structure](#directory-structure)
- [How to run?](#installation)
- [AWS-CICD-Deployment-with-Github-Actions](#usage)
- [Configuration](#configuration)

## Workflows

1. Update config.yaml
2. Update params.yaml
3. Update entity
4. Update the configuration manager in src config
5. update the conponents
6. update the pipeline
7. update the main.py
8. update the app.py

## Directory Structure
```
text-summarizer-project/
├── src/
│   ├── config/
│   │   ├── config_manager.py
│   ├── components/
│   │   ├── data_transformation.py
│   │   ├── model_trainer.py
│   ├── pipeline/
│   │   ├── stage_01_data_ingestion.ipynb
│   │   ├── stage_02_data_transformation.ipynb
│   │   ├── stage_03_model_training.ipynb
│   │   ├── stage_04_model_evaluation.ipynb
├── config.yaml
├── params.yaml
├── main.py
├── app.py
```

# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/entbappy/End-to-end-Text-Summarization
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n summary python=3.8 -y
```

```bash
conda activate summary
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```


```bash
Author: Krish Naik
Data Scientist
Email: krishnaik06@gmail.com

```



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/text-s

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
