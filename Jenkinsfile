pipeline {
    agent any

    stages {
        stage('Build') {
            sh 'test -f build/index.html'
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
    }
}
