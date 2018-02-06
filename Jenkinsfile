pipeline {
    agent any
    
    stages {
        stage('repo clean up'){
            steps {
                step([$class: 'WsCleanup'])
            }
        }

        stage('Checkout') {
            steps {
                git poll: true, url: 'https://github.com/dmall-k8s-microservice/dmall-inventory-service.git', branch: 'master'
            }
                
        }

        stage('Build') {
            steps{
                sh 'echo "building..."'
                sh 'echo "clean..."'
            }
        }
    }
}