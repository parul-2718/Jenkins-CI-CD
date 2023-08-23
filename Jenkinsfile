pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'modernengineeringdemojiraenviornment.atlassian.net'
                 }
             }
         }
         stage('Deploy - Staging') {
             when {

                   branch 'SCP-1-Develop'


             }
             steps {
                 echo 'Deploying to Staging from Develop...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-1', environmentName: 'us-stg-1', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {

                branch 'SCP-10-Develop'

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
