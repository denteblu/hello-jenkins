pipeline {
    agent { docker 'node:6.3' }
    environment {
      npm_config_cache='npm-cache'
      HOME='.'
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
                sh 'npm run test-jenkins'
            }
        }
    }
    post {
        always {
            junit 'build/reports/*.xml'
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        failure {
            echo 'I failed :('
        }
    }
}
