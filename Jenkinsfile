pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t kartikeya12rawat/jenkins-demo:%BUILD_NUMBER% .'
            }
        }

        stage('Check Credentials') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    bat 'echo USER=%DOCKER_USER%'
                }
            }
        }
    }
}