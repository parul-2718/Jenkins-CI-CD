pipeline { 
  
   agent any

   stages {
     stage('Deploy - Staging') {
             when {
                 branch 'main'
             }
             steps {
                 echo 'Deploying to Staging from master...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'us-stg-1', environmentName: 'us-stg-1', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {
                branch 'MTKDEMO-75-Develop'
            }
            steps {
                echo 'Deploying to Production from master...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'us-prod-1', environmentName: 'us-prod-1', environmentType: 'production'
                }
            }

           
     // stage('Build') {
     //         steps {
     //             echo 'Building...'
     //         }
     //   post {
     //             always {
     //                 jiraSendBuildInfo site: 'smartconnectedproductsmodernengineering.atlassian.net'
     //             }
     //        } 
     // }
     //     stage("Deploy application") { 
     //     steps { 
     //        echo "deploying application..."
     //     }

     // }
     
  
   	}

   }
}
