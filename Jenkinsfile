pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from Git repository
                git credentialsId:'8684275a-83a5-4fa5-8a21-f65facbf91b3', url: 'git@github.com/TharukshiDiyunugala/3918-Diyunugal.git'
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
