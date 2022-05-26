pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                npm ci
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
                sh 'dotnet test'
            }
        }
    }
}