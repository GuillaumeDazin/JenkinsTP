pipeline {
    agent any

    stages {
        stage('Deploy') {
            steps {
                retry(3) {
                    bat 'flakey-deploy.bat'
                }

                timeout(time: 3, unit: 'MINUTES') {
                    bat 'health-check.bat'
                }
            }
        }
    }
}
