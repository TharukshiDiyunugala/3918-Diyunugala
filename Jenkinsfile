pipeline {
    agent any
    environment {
        GIT_SSH_CREDENTIALS = credentials('devops-assignment-github-credentials')
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/master']],
                          userRemoteConfigs: [[url: 'git@github.com:TharukshiDiyunugala/3918-Diyunugal.git']],
                          credentialsId: 'devops-assignment-github-credentials'
                ])
            }
        }
    }
}
//
