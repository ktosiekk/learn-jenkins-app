pipeline {
    agent any

    stages {
        stage('Docker') {
            steps {
                sh '''
                docker build -t myapp-playwright .
                '''
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                node --version
                npm --version
                npm ci
                npm run build
                '''
            }
        }
        stage('E2E') {
            agent {
                docker {
                    image 'mcr.microsoft.com/playwright:v1.39.0-jammy'
                    reuseNode true
                    //args '-u root:root'
                }
            }
            steps {
                sh '''
                echo 'E2E TEST'
                '''
            }
        }
    }
}
