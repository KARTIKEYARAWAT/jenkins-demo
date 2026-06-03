pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t kartikeya12rawat/jenkins-demo:%BUILD_NUMBER% .'
            }
        }

        stage('Docker Login') {
    steps {
        withCredentials([usernamePassword(
            credentialsId: 'dockerhub-creds',
            usernameVariable: 'DOCKER_USER',
            passwordVariable: 'DOCKER_PASS'
        )]) {
            bat 'echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin'
        }
    }
}

        stage('Push Docker Image') {
            steps {
                bat 'docker push kartikeya12rawat/jenkins-demo:%BUILD_NUMBER%'
            }
        }
    }
}