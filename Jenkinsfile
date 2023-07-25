pipeline { 
  
   agent any

   stages {
     stage('Build') {
             steps {
                 echo 'Building...'
             }
     }
         stage("Deploy application") { 
         steps { 
            echo "deploying application..."
         }

     }
     post {
                 always {
                     jiraSendBuildInfo site: 'smartconnectedproductsmodernengineering.atlassian.net'
                 }
            } 
  
   	}

   }
