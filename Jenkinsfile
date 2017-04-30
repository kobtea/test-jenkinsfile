#!groovy
pipeline {
    agent any

    stages {
        stage('Print Env') {
            steps {
                sh "env"
            }
        }

        stage('ls master') {
            steps {
                sh 'ls -l'
            }
        }

        stage('checkout other branch') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/foo-branch']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: 'https://github.com/kobtea/test-jenkinsfile.git']]
                ])
            }
        }

        stage('ls foo-branch') {
            steps {
                sh 'ls -l'
            }
        }

        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
