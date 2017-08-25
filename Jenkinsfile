pipeline {
    agent { docker 'node:6.3' }
    environment {
      npm_config_cache=npm-cache
      HOME=.
    }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
                sh 'npm install'
            }
        }
        stage('test') {
            steps {
                sh './script/test'
            }
        }
    }
}
