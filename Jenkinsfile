#!groovy
pipeline {
    agent any

    stages {
        stage('Check branch') {
            steps {
                echo 'this branch is' + env.BRANCH_NAME
                sh 'ls -l'
            }
        }

        stage('Kick other branches') {
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

        stage('Checkout from master branch') {
            steps {
                script {
                    if (env.BRANCH_NAME != 'master') {
                        sh 'git checkout origin/master -- master.txt'
                        sh 'ls -l'
                    }
                }
            }
        }
    }
}
