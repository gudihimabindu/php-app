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
   stage('Sonarqube report') {
    sh sonar-scanner \
     -Dsonar.projectKey=com.corelight \
     -Dsonar.sources=src \
     -Dsonar.host.url=http://ec2-18-188-125-184.us-east-2.compute.amazonaws.com:9000/ \
     -Dsonar.login=de4fa88afb82c62edf8942c271ae8071d3b8025b
   }
 }
}