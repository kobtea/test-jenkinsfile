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
                echo 'this is master'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
