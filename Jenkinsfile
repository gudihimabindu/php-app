pipeline {
  agent any
   options {
    disableConcurrentBuilds()
    buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '5'))
   }

 stages {
    stage('SCM Checkout') {
      steps {
        script {
            git credentialsId: '62fad565-6f44-4f5f-a7c1-62297b0c73bb', url: 'https://github.com/gudihimabindu/php-app.git'
            
         }
      }   
     }
   }
}