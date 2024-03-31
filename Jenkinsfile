pipeline {
    agent { label 'linux' }
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker build -t test-1/dp-alpine:latest .'
                }
            }
        }
        stage('Push') {
            steps {
                script {
                    sh 'docker push test-1/dp-alpine:latest'
                }
            }
        }
    }
}
