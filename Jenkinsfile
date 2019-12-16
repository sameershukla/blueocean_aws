pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-east-2') {
          sh 'echo "Uploading content with AWS creds"'
          s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file: 'index.html', bucket: 'udagram-assigment-2')
        }

      }
    }

  }
}