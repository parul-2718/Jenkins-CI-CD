pipeline { 
  
   agent any
  stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'smartconnectedproductsmodernengineering.atlassian.net'
                 }
             }
         }
         stage('Deploy - Staging') {
             when {
                   branch 'MTKDEMO-82-Develop'
             }
             steps {
                 echo 'Deploying to Staging from Develop...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-12', environmentName: 'us-stg-12', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {
                branch 'MTKDEMO-77-Develop'
            }
            steps {
                echo 'Deploying to Production from Develop...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-12', environmentName: 'us-prod-12', environmentType: 'production'
                }
            }
         }
     }

  
}
