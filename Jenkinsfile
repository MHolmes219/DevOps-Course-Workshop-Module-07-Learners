pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                script {
                    npm ci
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Building the app'
                dotnet build
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the app'
                dotnet test
            }
        }
    }
}