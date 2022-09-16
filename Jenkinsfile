pipeline {
  agent any
  stages {
    stage('deploy stack') {
      environment {
        STACK_NAME = 'philosophy'
        S3_BUCKET = 'gijanehaug'
      }
      steps {
        withAWS(credentials: 'aws', region: 'us-east-2') {
          unstash 'venv'
          unstash 'aws-sam'
          sh 'sam deploy --stack-name philosophy -t template.yaml --s3-bucket gijanehaug --capabilities CAPABILITY_IAM'
        }
      }
    }
  }
}