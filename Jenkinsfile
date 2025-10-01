pipeline {
    agent any
    stages {
        stage('checkout-1') {
            steps {
                git branch: 'main',
                credentialsId: 'jenkins-github', 
                url: 'https://github.com/jai250/jenkins-pipeline.git'

            }
        }

        stage('testing build') {
            steps {
                sh '''
                   ls -lrt
                   pwd
                   echo "testing for git
                   exit 1 "
                   '''
            }
        }

        stage('checkout-2') {
            steps {
                checkout scmGit(branches: [[name: '*/main']],
                extensions: [], userRemoteConfigs: [[credentialsId: 'jenkins-github', 
                url: 'https://github.com/jai250/jenkins-pipeline_2.git']])
            }
        }

        stage('testing build-2') {
            steps {
                sh '''
                   ls -lrt
                   pwd
                   echo "this is checkout"
                   '''
            }   
        }
    }
}