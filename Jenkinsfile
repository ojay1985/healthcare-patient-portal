pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Safety Check') {
            steps {
                bat '''
                echo Checking Healthcare Patient Portal files

                IF NOT EXIST index.html (
                  echo ERROR: index.html is missing!
                  exit /b 1
                )

                echo File check passed
                '''
            }
        }

        stage('Deploy to Hospital Test Server') {
            steps {
                bat '''
                echo Deploying to hospital test server

                IF NOT EXIST C:\\hospital-test-server (
                  mkdir C:\\hospital-test-server
                )

                copy index.html C:\\hospital-test-server\\index.html

                echo Deployment completed
                '''
            }
        }
    }
}
