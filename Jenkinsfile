pipeline {
    agent any

    environment {
        APP_NAME = 'JenkinsTP'
        APP_VERSION = '1.0'
        DATABASE = 'MySQL'
    }

    stages {
        stage('Display Global Variables') {
            steps {
                echo "Application : ${env.APP_NAME}"
                echo "Version : ${env.APP_VERSION}"
                echo "Base de donnees : ${env.DATABASE}"
            }
        }

        stage('Display Jenkins Variables') {
            steps {
                echo "Build numero : ${env.BUILD_NUMBER}"
                echo "Nom du job : ${env.JOB_NAME}"
                echo "Workspace : ${env.WORKSPACE}"
            }
        }

        stage('Local Environment') {
            environment {
                ENVIRONMENT = 'Testing'
            }
            steps {
                echo "Environnement : ${env.ENVIRONMENT}"
                echo "Application : ${env.APP_NAME}"
            }
        }
    }
}
