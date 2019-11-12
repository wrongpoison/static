pipeline {
  agent any
  stages {
    stage('Test Pipeline'){
        steps{
            sh 'echo "Pipeline executing"'
        }
    }
    stage('Upload to AWS') {
      steps {
          withAWS(region:'us-east-2', credentials:'Static HTML publisher in AWS') {
              s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'devopscourse3jenkins')
          }
      }
    }
  }
}