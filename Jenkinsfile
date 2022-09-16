pipeline {
  agent any
  stages {
    stage('deploy stack') {
      steps {
        sh 'sam deploy --stack-name philosophy -t template.yaml --s3-bucket gijanehaug --capabilities CAPABILITY_IAM'
        }
      }
    }
  }