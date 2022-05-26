pipeline {
    agent none

    stages {
        stage('Dependencies') {
            agent { docker "node:17-bullseye" }
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