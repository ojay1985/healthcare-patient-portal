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
    }
}

