pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application...'

                bat '''
                    if not exist build\\libs mkdir build\\libs
                    echo This is a simulated build artifact > build\\libs\\application.jar
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'

                powershell '''
                    New-Item -ItemType Directory -Force -Path "build/test-results" | Out-Null

                    @"
<?xml version="1.0" encoding="UTF-8"?>
<testsuite tests="2" failures="0" errors="0" skipped="0">
    <testcase classname="ExampleTest" name="testExample1"/>
    <testcase classname="ExampleTest" name="testExample2"/>
</testsuite>
"@ | Set-Content -Path "build/test-results/results.xml" -Encoding UTF8
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
