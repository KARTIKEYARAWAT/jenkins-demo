pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-demo:%BUILD_NUMBER% .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f demo-container || exit 0'
                bat 'docker run -d -p 8090:80 --name demo-container jenkins-demo:%BUILD_NUMBER%'
            }
        }

        
    }
}