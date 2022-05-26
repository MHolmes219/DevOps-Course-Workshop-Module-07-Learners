pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                echo 'Installing npm'
                npm --version
            }
        }
        stage('Build') {
            steps {
                echo 'Building the app'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the app'
            }
        }
    }
}