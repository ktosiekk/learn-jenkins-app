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
    }
}
