pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm ci'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the app'
                sh 'dotnet build'
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