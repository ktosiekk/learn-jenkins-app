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
                    image 'node:18-alpine'
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
