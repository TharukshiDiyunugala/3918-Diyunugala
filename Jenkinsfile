pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from Git repository
                git 'https://github.com/TharukshiDiyunugala/3918-Diyunugal'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    docker.build("devops-assignment:${env.BUILD_NUMBER}")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run Docker container
                    docker.image("devops-assignment-app:${env.BUILD_NUMBER}")
                        .run("-p 8888:80")
                        .name("devops-assignment-container")
                }
            }
        }
    }
}