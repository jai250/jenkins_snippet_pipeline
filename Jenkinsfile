pipeline {
    agent any


 environment {
        GIT_BRANCH = 'main'
        GIT_CREDS = 'jenkins-github' 
        REPO_URL = 'https://github.com/jai250/jenkins-pipeline.git'
        
    }



    parameters {
  choice choices: ['https://github.com/jai250/jenkins-pipeline.git', 'https://github.com/jai250/jenkins-pipeline_2.git'], description: 'select from 1sdt and 2nd pipiline', name: 'REPO_URL'
  choice choices: ['test ', 'stagging', 'prod'], name: 'environment'
  string defaultValue: 'main', name: 'GIT_BRANCH'
}
    

   



    stages {
        stage('checkout-groovy') {
            steps {
                // groovy syntax
                git branch: "${env.GIT_BRANCH}",
                credentialsId: "${env.GIT_CREDS}", 
                url: "${params.REPO_URL}"

            }
        }

        stage('shell syntax') {
            steps {
                sh """
                   echo $GIT_BRANCH
                   echo $GIT_CREDS
                   echo "${params.REPO_URL}"
                   """
                
            }
        }
    }
}