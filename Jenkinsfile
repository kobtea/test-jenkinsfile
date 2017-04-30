#!groovy
pipeline {
    agent any

    stages {
        stage('Check branch') {
            steps {
                echo env.BRANCH_NAME
                sh 'ls -l'
            }
        }

        stage('Only Master stage') {
            steps {
                if (env.BRANCH_NAME == 'master') {
                    echo 'this is master'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
