pipeline { 
  
   agent any

   stages {
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy application") { 
         steps { 
           sh 'echo "deploying application..."'
         }

     }
     post {
                 always {
                     jiraSendBuildInfo site: 'smartconnectedproductsmodernengineering.atlassian.net', branch: 'MTKDEMO-75-Develop'
                 }
            } 
  
   	}

   }
