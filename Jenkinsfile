pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'modernengineeringdemojiraenviornment.atlassian.net', branch: 'SCP-78-Develop'
                 }
             }
         }
         stage('Deploy - Staging') {
           
             steps {
                 echo 'Deploying to Staging from Develop...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-22', environmentName: 'us-stg-22', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {
                branch 'SCP-78-Develop'
            }
            steps {
                echo 'Deploying to Production from Develop...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-23', environmentName: 'us-prod-23', environmentType: 'production'
                }
            }
         }
     }

  
}
