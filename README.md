# Boston Housing Price Prediction Microservice

This project involves operationalizing a pre-trained Scikit-learn model for predicting housing prices in Boston using a Python Flask application, Docker, and Jenkins for CI/CD. The goal is to containerize the application, deploy it, and automate the build process using Jenkins.

## Project Structure

```
.
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
└── README.md
```

## Step-by-Step Instructions

### 1. Initialize Git Repository

First, initialize the code directory as a Git repository and make your initial commit.

```bash
git init
git add .
git commit -m "Initial commit"
```

### 2. Complete the Dockerfile

Create a Dockerfile to containerize the application. The Dockerfile should contain the following:

```Dockerfile
FROM python:3.7.3-stretch

## Step 1:
# Create a working directory
WORKDIR /app

## Step 2:
# Copy source code to working directory
COPY . app.py /app/

## Step 3:
# Install packages from requirements.txt
# hadolint ignore=DL3013
RUN pip install --upgrade pip && pip install -r requirements.txt

## Step 4:
# Expose port 80
EXPOSE 80

## Step 5:
# Run app.py at container launch
CMD ["python", "app.py"]

```

### 3. Build and Run the Docker Container

Build the Docker image and run the container.

```bash
docker build -t boston-housing-predictor .
docker run -p 5000:5000 boston-housing-predictor
```


### 4. Complete the Jenkinsfile

Create a Jenkinsfile to automate the build and publish process. The Jenkinsfile should contain the following:

```groovy
pipeline {
    agent any

    environment {
        // Use Jenkins credentials plugin to handle Docker Hub credentials
        DOCKER_HUB_CREDENTIALS = credentials('docker-hub-credentials')
    }

    stages {
        stage('Build Image') {
            steps {
                script {
                    // Build the Docker image from the Dockerfile
                    dockerImage = docker.build("nachia2024/boston-housing-predictor:${env.BUILD_NUMBER}")
                }
            }
        }
        stage('Publish Image') {
            steps {
                script {
                    // Login to Docker Hub and push the image
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        dockerImage.push("${env.BUILD_NUMBER}")
                        dockerImage.push("latest")
                    }
                }
            }
        }
    }
}

```

### 5. Setup Jenkins

1. **Install Jenkins:**
   Follow the official Jenkins installation guide for your operating system [here](https://www.jenkins.io/doc/book/installing/).

2. **Install Docker Plugin:**
   Go to `Manage Jenkins` > `Manage Plugins` > `Available` and search for `Docker Plugin`, then install it.

3. **Configure Docker in Jenkins:**
   Go to `Manage Jenkins` > `Global Tool Configuration` and add Docker installations if needed.

4. **Create a New Pipeline Job:**
   - Go to `Jenkins` > `New Item` > `Pipeline`.
   - Name your job (e.g., `boston-housing-predictor-pipeline`).
   - In the Pipeline section, choose `Pipeline script from SCM`.
   - Set SCM to `Git` and provide the repository URL (`https://github.com/yourusername/boston-housing-predictor.git`).
   - Specify the branch to build (e.g., `*/master`).
   - Path to the Jenkinsfile (`Jenkinsfile`).

### 6. Push to GitHub

After completing the above steps, push your code to GitHub. Make sure to create meaningful commits.

```bash
git add .
git commit -m "Added Dockerfile and Jenkinsfile"
git remote add origin https://github.com/yourusername/boston-housing-predictor.git
git push -u origin master
```

### Example Response

```json
{
    "Sklearn Prediction Home
}
```

This concludes the setup and operationalization of the Boston Housing Price Prediction microservice using Flask, Docker, and Jenkins. Follow the instructions step-by-step to replicate the project.
```

