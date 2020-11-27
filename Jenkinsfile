pipeline {
 agent any
 
 stages {
   stage('Build docker image') {
     steps {
        sh 'docker build -t cyberfrat1 .'
        }
      }
   stage('Test Run') {
      steps {
          sh 'docker run -d cyberfrat'
          }
        }
      }
   }
   
