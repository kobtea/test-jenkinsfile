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
                script {
                    if (env.BRANCH_NAME == 'master') {
                        echo 'this is master'
                        def branches = sh(script: 'git branch -r | egrep -v "HEAD|master" | awk -F"/" \'{print $NF}\'', returnStdout: true).trim().tokenize('\r?\n')
                        for (branch in branches) {
                            build './' + branch
                        }
                    }
                }
            }
        }
    }
}
