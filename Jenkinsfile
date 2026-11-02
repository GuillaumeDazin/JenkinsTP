pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'

                bat '''
                    mkdir build\\libs
                    echo This is a simulated build artifact > build\\libs\\application.jar
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'

                bat '''
                    mkdir build\\test-results
                    echo ^<?xml version="1.0" encoding="UTF-8"?^> > build\\test-results\\results.xml
                    echo ^<testsuite tests="2" failures="0" errors="0" skipped="0"^> >> build\\test-results\\results.xml
                    echo ^<testcase classname="ExampleTest" name="testExample1"/^> >> build\\test-results\\results.xml
                    echo ^<testcase classname="ExampleTest" name="testExample2"/^> >> build\\test-results\\results.xml
                    echo ^</testsuite^> >> build\\test-results\\results.xml
                '''
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/test-results/**/*.xml'
        }
    }
}
