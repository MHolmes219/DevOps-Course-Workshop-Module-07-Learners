pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                echo 'Installing npm'
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