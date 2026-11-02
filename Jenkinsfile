pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                bat '''
                    mkdir build\\test-results
                    echo ^<?xml version="1.0" encoding="UTF-8"?^> > build\\test-results\\results.xml
                    echo ^<testsuite tests="1" failures="0" errors="0" skipped="0"^> >> build\\test-results\\results.xml
                    echo ^<testcase classname="ExampleTest" name="testExample"/^> >> build\\test-results\\results.xml
                    echo ^</testsuite^> >> build\\test-results\\results.xml
                '''
            }
        }
    }

    post {
        always {
            junit 'build/test-results/**/*.xml'
        }
    }
}
