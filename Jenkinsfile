pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'modernengineeringdemojiraenviornment.atlassian.net', branch: 'SCP-79-Develop'
                 }
             }
         }
         stage('Deploy - Staging') {
            // when {
            //     branch 'SCP-79-Develop'
            // }
             steps {
                 echo 'Deploying to Staging from Develop...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-24', environmentName: 'us-stg-24', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            // when {
            //     branch 'SCP-79-Develop'
            // }
            steps {
                echo 'Deploying to Production from Develop...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-25', environmentName: 'us-prod-25', environmentType: 'production'
                }
            }
         }
     }

  
}
