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
         stage("Deploy application") { 
         steps { 
            echo "deploying application..."
         }

     }
     
  
   	}

   }
