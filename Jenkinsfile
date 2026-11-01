pipeline {
    agent any

    stages {
        stage('Check Agent') {
            steps {
                echo 'Verification de l agent Jenkins'

                bat 'hostname'
                bat 'java -version'
            }
        }

        stage('Environment') {
            steps {
                echo 'Verification de l environnement'

                bat 'echo Nous sommes sur Windows'
            }
        }
    }
}
