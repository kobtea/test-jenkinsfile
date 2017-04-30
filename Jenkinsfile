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
                if (true) {
                    echo 'this is master'
                }
                echo 'hoge'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
