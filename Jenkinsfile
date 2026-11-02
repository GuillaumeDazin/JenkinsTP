pipeline {
    agent any

    stages {
        /* "Build" and "Test" stages omitted */

        stage('Deploy - Staging') {
            steps {
                bat 'echo Deploying to staging...'
                bat 'echo Running smoke tests...'
            }
        }

        stage('Sanity check') {
            steps {
                input message: 'Does the staging environment look ok?'
            }
        }

        stage('Deploy - Production') {
            steps {
                bat 'echo Deploying to production...'
            }
        }
    }
}
