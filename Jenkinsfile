pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                bat 'node --eval "console.log(process.arch,process.platform)"'
            }
        }
    }
}
