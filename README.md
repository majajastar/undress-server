
# Undress Game Server

This repository contains a **CI/CD pipeline** for deploying a Node.js application to **AWS Elastic Beanstalk** using **GitHub Actions**. The pipeline is triggered on any push or pull request to the `main` branch.

## Server Address: 
```
ws://Undress-game-server-env.eba-4g23hqie.ap-southeast-1.elasticbeanstalk.com:9900
```
---

## Requirements

Before setting up the CI/CD pipeline, make sure you have the following:

### 1. **AWS Account and Elastic Beanstalk Application**
- Create an **AWS account** if you don't already have one.
- Set up an **Elastic Beanstalk application** with **Node.js 18** as the platform.
- Create an environment for your application (e.g., `Undress-game-server-env`).

### 2. **GitHub Repository Secrets**
In order to securely store your AWS credentials, you'll need to add them as secrets to your GitHub repository:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION` (e.g., `ap-southeast-1`)

#### To add GitHub Secrets:
1. Go to **Settings** → **Secrets and variables** → **Actions**.
2. Add each secret by clicking **New repository secret**.

### 3.Install dependencies
``` bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```
## EB CLI Commands for Deployment

These are the commands needed to manually deploy your application to **AWS Elastic Beanstalk**.

### Step 1: Initialize EB CLI

To set up your Elastic Beanstalk application, run the following command from the root of your project:

```bash
eb init --platform "Node.js 18 running on 64bit Amazon Linux 2023" --region <AWS_REGION> <EB_APPLICATION_NAME>
```
- Replace <AWS_REGION> with your desired AWS region (e.g., ap-southeast-1).
- Replace <EB_APPLICATION_NAME> with the name of your Elastic Beanstalk application.
### Step 2: Select EB Environment
After initializing EB CLI, use the following command to specify which Elastic Beanstalk environment you want to deploy to:
```bash
eb use <EB_ENVIRONMENT_NAME>
```
### Step 3: Deploy to EB
```bash
eb deploy
```

