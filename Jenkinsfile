pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps{
                sh './gradlew clean build'
            }
        }

        stage('Docker image') {
            steps{
                sh './genImages.sh'
            }
        }

        stage('Deploy to DEV') {
            steps{
                withCredentials([[$class: 'FileBinding', credentialsId: 'kubectl-config-file', variable: 'KUBECTL_CONFIG_FILE']]) {
                    sh './deployToDEV.sh'
                }
            }
        }
    }
}