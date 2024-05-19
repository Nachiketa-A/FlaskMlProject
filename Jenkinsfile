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
