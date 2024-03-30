pipeline {
    agent { laber 'linux'}
    options {
      buildDiscarder (logRotator{ numToKeepStr: '5')}
        }
      environment {
        DOCKERHUB_CREDENTIALS = credentials ('dockerhub')
      }
      stage('Build') {
            steps {
                sh ' docker build -t test-1/dp-alpine:latest .'
            }
        }
      stage('Push') {
            steps {
                sh ' docker push test-1/dp-alpine:latest '
            }
        } 
  }
  
