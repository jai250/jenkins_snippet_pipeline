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
        stage('running parallel') {
            parallel {
                stage('testing build') {
                    steps {
                        sh '''
                        ls -lrt
                        pwd
                        echo "testing for parallel-1"
                        sleep 10
                        '''
                    }
                }

                stage('testing build-2') {
                    steps {
                        sh '''
                        echo $USER
                        pwd
                        echo "this is parallel-2"
                        sleep 10
                        '''
                    }   
                }
            }
        }        
    }
}