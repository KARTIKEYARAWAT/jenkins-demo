pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t kartikeya12rawat/jenkins-demo:%BUILD_NUMBER% .'
            }
        }

        // stage('Run Container') {
        //     steps {
        //         bat 'docker rm -f demo-container || exit 0'
        //         bat 'docker run -d -p 8090:80 --name demo-container jenkins-demo:%BUILD_NUMBER%'
        //     }
        // }
        
        stage('Push to Docker Hub'){
            steps{
                bat 'docker push kartikeya12rawat/jenkins-demo:%BUILD_NUMBER%'
            }
        }
        
    }
}