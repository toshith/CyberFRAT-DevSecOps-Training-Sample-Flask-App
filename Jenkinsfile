pipeline {
 environment{
    registry= "toshith/devsecops-training"
    registryCredential = "DockerHub"
    dockerImage = ''
  }
 agent any
 
 stages {
   stage('Build docker image') {
     steps {
      script {
            dockerImage= docker.build registry + ":$BUILD_NUMBER"
          }       
        }
      }
  stage ('Push to docker Hub') {
   steps {
    script {
         docker.withRegistry('', registryCredential ) {
          dockerImage.push()
         }
       }
     }
  }
       
   stage('Test Run') {
      steps {
        sh 'docker run -d registry:$BUILD_NUMBER'          
          }
        }
      }
   }
   
