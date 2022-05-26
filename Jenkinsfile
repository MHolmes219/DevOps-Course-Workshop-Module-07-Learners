pipeline {
    agent any

    stages {
        stage('Dependencies') {
            steps {
                echo 'Installing npm'
                sh '''
                npm --version
                '''
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