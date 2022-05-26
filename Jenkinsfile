pipeline {
    agent none

    stages {
        stage('Dependencies') {
            agent { 'node:17-bullseye' }
            steps {
                npm ci
            }
        }
        stage('Build') {
            agent any
            steps {
                echo 'Building the app'
                dotnet build
            }
        }
        stage('Test') {
            agent any
            steps {
                echo 'Testing the app'
                sh 'dotnet test'
            }
        }
    }
}