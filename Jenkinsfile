pipeline {
agent any
   stages {
       stage('Build') {
         steps {
           sh 'g++ tri.cpp -o output'
           build 'PES1UG20CS696-1'
           echo 'Build Stage Successful'
         }
       }
       stage('Test') {
         steps {
           sh './output'
           echo 'Test Stage Successful'
         }
       }
     stage('Deploy') {
       when {
         expression {
          currentBuild.result == null || currentBuild.result == 'SUCCESS'
         }
       }
       steps {
         echo 'Deployment Successful'
       }
     }
 }
 post {
   failure {
     echo 'Pipeline failed'
   }
 }
}
