pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                bat 'echo Fail! & exit /b 1'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
