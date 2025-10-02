pipeline {
    agent any

    parameters {
  choice choices: ['https://github.com/jai250/jenkins-pipeline.git', 'https://github.com/jai250/jenkins-pipeline_2.git'], description: 'select from 1sdt and 2nd pipiline', name: 'URL'
  choice choices: ['test ', 'deploy', 'prod'], name: 'environment'
  string 'pipeline job'
}
    

    environment {
        GIT_BRANCH = 'main'
        GIT_CREDS = 'jenkins-github' 
        REPO_URL = 'https://github.com/jai250/jenkins-pipeline.git'
        
    }



    stages {
        stage('checkout-groovy') {
            steps {
                // groovy syntax
                git branch: "${env.GIT_BRANCH}",
                credentialsId: "${env.GIT_CREDS}", 
                url: "${env.REPO_URL}"

            }
        }

        stage('shell syntax') {
            steps {
                sh '''
                   echo $GIT_BRANCH
                   echo $GIT_CREDS
                   echo $REPO_URL
                   '''
                
            }
        }
    }
}