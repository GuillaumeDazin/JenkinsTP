pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                echo 'Preparation du projet'
                bat 'echo Verification de l environnement'
            }
        }

        stage('Build') {
            steps {
                echo 'Compilation du projet'
                bat 'echo Build termine'
            }
        }

        stage('Test') {
            steps {
                echo 'Execution des tests'
                bat 'echo Tests termines'
            }
        }
    }

    post {
        success {
            echo 'Pipeline terminee avec succes !'
        }

        failure {
            echo 'La pipeline a echoue.'
        }
    }
}
