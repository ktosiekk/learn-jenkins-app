pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                test -f build/index.html
                node --version
                npm --version
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
