pipeline {
    agent { docker 'node:6.3' }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
            }
            steps {
                sh 'npm install'
            }
            steps {
                sh './script/test'
            }
        }
    }
}
