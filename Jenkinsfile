pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo '1 - 2 - 3'
                '''
            }
        }
        stage('Build2') {
            agent {
                docker {
                    image 'alpine:3.14'
                }
            }
            steps {
                sh '''
                node --version
                npm --version
                '''
            }
        }
    }
}
