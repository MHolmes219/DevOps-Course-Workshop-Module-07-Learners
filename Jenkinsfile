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
                        dir('DotnetTemplate.Web') {
                            sh "pwd"
                            echo 'Installing npm'
                            sh "npm install"
                        }
                    }
                }
                stage("build") {
                    steps {
                        dir('DotnetTemplate.Web') {
                            echo 'Build npm'
                            sh "npm run build"
                        }
                    }
                }
                stage("line") {
                    steps {
                        dir('DotnetTemplate.Web') {
                            echo 'Lint npm'
                            sh "npm run lint"
                        }
                    }
                }
                stage("test") {
                    steps {
                        dir('DotnetTemplate.Web') {
                            echo 'Test npm'
                            sh "npm t"
                        }
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
                        sh "dotnet build"
                    }
                }
                stage('test') {
                    steps {
                        echo 'Testing the app'
                        sh "dotnet test"
                    }
                }
            }
        }
    }
}