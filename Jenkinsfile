pipeline {
  agent any
  @Library('github.com/releaseworks/jenkinslib')
  stages {
    stage('beta') {
      environment {
        STACK_NAME = 'philosophy'
        S3_BUCKET = 'gijanehaug'
      }
      steps {
        withAWS(credentials: 'aws', region: 'us-east-2') {
          sh 'sam deploy --stack-name $STACK_NAME -t template.yaml --s3-bucket $S3_BUCKET --capabilities CAPABILITY_IAM'
        }
      }
    }
  }
}