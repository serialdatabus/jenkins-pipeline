pipeline {
    environment {
        registry = "serialbus/jenkins-docker-test"
        DOCKER_PWD = "Uezile2022!"
    }
    agent {
        docker {
            image 'node:16.13.1-alpine'
            args '-p 3000:3000'
            args '-w /app'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage("Build"){
            steps {
                sh 'npm install'
            }
        }
        stage("Test"){
            steps {
                sh 'npm test'
            }
        }
    }
}