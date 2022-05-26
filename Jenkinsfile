pipeline {
    agent none

    environment {
        DOTNET_CLI_HOME = "/tmp/dotnet_cli_home"
    }

    stages {
        stage('Install, build & test node') {
            agent {
                docker "node:17-bullseye"
            }
            stages {
                stage("dependencies") {
                    steps {
                        echo 'Installing npm'
                        sh '''
                        npm ci
                        '''
                    }
                }
               stage("build") {
                   steps {
                       echo 'Build npm'
                        sh '''
                        npm run build
                        '''
                   }
               }
               stage("line") {
                   steps {
                       echo 'Lint npm'
                        sh '''
                        npm run lint
                        '''
                   }
               }
               stage("test") {
                   steps {
                       echo 'Test npm'
                        sh '''
                        npm t
                        '''
                   }
               }
            }
        }
        stage('Build & test the .net app') {
            agent {
                docker "mcr.microsoft.com/dotnet/sdk"
            }
            stages {
                stage('build') {
                    steps {
                        echo 'Building the app'
                        sh '''
                        dotnet build
                        '''
                    }
                }
                stage('test') {
                    steps {
                        echo 'Testing the app'
                        sh '''
                        dotnet test
                        '''
                    }
                }
            }
        }
    }
}