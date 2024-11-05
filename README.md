# Chicken_Disease_Classification

## Project Overview
  This project aims to classify images of chickens to detect coccidiosis, a common parasitic disease, using a Convolutional Neural Network (CNN) architecture. For this task, we used VGG16, a pre-trained deep learning model, fine-tuning it for our specific dataset. This project can help identify early signs of coccidiosis, aiding poultry farmers in disease management.

## Dataset
  We created a custom dataset consisting of images of chickens affected by coccidiosis. This self-made dataset contains labeled images for the presence of disease, making it a binary classification task.

  - Classes: Coccidiosis and Healthy
  - Data Preprocessing:
     - Image Resizing: All images were resized to match the input size of VGG16.
     - Normalization: Pixel values were normalized to improve model performance.
     - Augmentation: Techniques like rotation, zoom, and flip were used to increase variability.

## Model Architecture
  The model uses a VGG16 architecture, a 16-layer CNN pre-trained on ImageNet, which was fine-tuned for our dataset. We replaced the final dense layers of VGG16 to better suit this binary classification problem.

#### Model Summary
   1) Base Model: VGG16 (pre-trained on ImageNet)
   2) Additional Layers:
     - Dropout layers to reduce overfitting
     - Fully connected layers with ReLU activation
     - Output layer with sigmoid activation for binary classification
   3) Loss Function: Binary Cross-Entropy
   4) Optimizer: Adam Optimizer with learning rate tuning


## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml


# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Yogesh3454/Chicken_Disease_Classification
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n cnncls python=3.8 -y
```

```bash
conda activate cnncls
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```
Ensure you have Python 3.7+ and pip installed. Key dependencies:

- tensorflow
- keras
- numpy
- pandas
- matplotlib


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```


### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag



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
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken

	
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




# AZURE-CICD-Deployment-with-Github-Actions

## Save pass:

s3cEZKH5yytiVnJ3h+eI3qhhzf9q1vNwEi6+q+WGdd+ACRCZ7JD6


## Run from terminal:

docker build -t chickenapp.azurecr.io/chicken:latest .

docker login chickenapp.azurecr.io

docker push chickenapp.azurecr.io/chicken:latest


## Deployment Steps:

1. Build the Docker image of the Source Code
2. Push the Docker image to Container Registry
3. Launch the Web App Server in Azure 
4. Pull the Docker image from the container registry to Web App server and run 
