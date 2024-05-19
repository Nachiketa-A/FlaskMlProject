pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                script {
                    // Build the Docker image from the Dockerfile
                    dockerImage = docker.build("boston-housing-predictor")
                }
            }
        }
        stage('Publish Image') {
            steps {
                script {
                    // Publish the Docker image to Dockerhub
                    // Note: Actual publishing is not required as per the instructions
                    withDockerRegistry([ credentialsId: "docker-hub-credentials", url: "" ]) {
                        dockerImage.push("${env.BUILD_NUMBER}")
                        dockerImage.push("latest")
                    }
                }
            }
        }
    }
}
