pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'toolkittesting.atlassian.net'
                 }
             }
         }
         stage('Deploy - Staging') {
             when {
                   branch 'MT-11'
             }
             steps {
                 echo 'Deploying to Staging from Develop...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-20', environmentName: 'us-stg-20', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {
                branch 'MT-11'
            }
            steps {
                echo 'Deploying to Production from Develop...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-2', environmentName: 'us-prod-2', environmentType: 'production'
                }
            }
         }
     }

  
}
