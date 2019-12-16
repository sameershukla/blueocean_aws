pipeline {
  agent any
  stages {
    stage('Lint HTML') {
		tidy -q -e *.html
	}
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-east-2', credentials: 'user-creds') {
          sh 'echo "Uploading content with AWS creds"'
          s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file: 'index.html', bucket: 'udagram-assigment-2')
        }

      }
    }

  }
}