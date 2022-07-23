
[![CircleCI](https://dl.circleci.com/status-badge/img/gh/onyiafranklin/Operationalise_ML_MICROSERVICE_API/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/onyiafranklin/Operationalise_ML_MICROSERVICE_API/tree/master)

## Project Overview

In this project, I used the skill I acquired  in this course to operationalize a Machine Learning Microservice API. 

Given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

## Setup the Environment

*  I created  a virtualenv with Python 3.7 and activated it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* I Ran `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
### Explanation of files
1. circleci/config.yml ---- circleci configuration

2. Dockerfile ---- Docker configuration file

3. make_prediction.sh ---- A script for  logging  predictions endpoint output

4. Makefile ---- This contains instructions on environment setup,dependencies installation instruction, and lint tests

5. requirements.txt ---- This contains python dependencies for the project

6. run_docker.sh ---- A shell script to build docker image and run it

7. model_data ---- contains housing prices in Boston area

8. output_txt_files/docker_out.txt ---- contains docker log outputs

9. output_txt_files/kubernetes_out.txt ---- contains kubernetes log outputs

10. app.py - flask app API endpoint with routes to get house prices in Boston


11. run_kubernetes.sh ----- A  shell script for  running   Docker Hub container with kubernetes

12. upload_docker.sh ---- A  shell script for  uploading local docker build image to docker hub that is online.
