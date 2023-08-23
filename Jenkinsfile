pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'modernengineeringdemojiraenviornment.atlassian.net', branch: 'SCP-77-Develop'
                 }
             }
         }
         stage('Deploy - Staging') {
           
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
            // when {
            //     branch 'SCP-77-Develop'
            // }
            steps {
                echo 'Deploying to Production from Develop...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-21', environmentName: 'us-prod-21', environmentType: 'production'
                }
            }
         }
     }

  
}
