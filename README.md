# 🐔 Chicken Disease Classification – End-to-End MLOps Project

This project implements a deep-learning and MLOps workflow for Chicken Disease Classification using CNN, DVC, Docker, AWS, and GitHub Actions.

## Project Workflow

- Update `config.yaml`  
- Update `secrets.yaml` (optional)  
- Update `params.yaml`  
- Update entity files  
- Update configuration manager (`src/config`)  
- Update components  
- Update pipeline script  
- Update `main.py`  
- Update `dvc.yaml`  

## How to Run the Project

### 1. Clone the Repository
```bash
git clone <your_repo_link_here>
cd <your_repo_name>
```

### 2. Create a Conda Environment
```bash
conda create -n cnncls python=3.8 -y
conda activate cnncls
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
python app.py
```
Open your localhost to use the app.

## DVC Commands
```bash
dvc init
dvc repro
dvc dag
```

## AWS CICD Deployment (GitHub Actions)

1. Login to AWS  
2. Create IAM User for Deployment with permissions:
   - AmazonEC2FullAccess  
   - AmazonEC2ContainerRegistryFullAccess  
3. Create ECR Repository  
   ```
   <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repo_name>
   ```
4. Create EC2 (Ubuntu)  
5. Install Docker on EC2
```bash
sudo apt-get update -y
sudo apt-get upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```
6. Configure EC2 as Self-Hosted Runner on GitHub  
7. Add GitHub Secrets
```
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION=us-east-1
AWS_ECR_LOGIN_URI=<your_ecr_login_uri>
ECR_REPOSITORY_NAME=<your_repo_name>
```
