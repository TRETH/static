pipeline{
    agent any
    stages {
        stage('Upload to AWS')  {
            steps {
                withAWS(credentials: 'aws-static', region: 'eu-central-1'){
                    s3Upload(bucket: 'udacity-pipeline-project', workingDir:'build', includePathPattern:'**/*');
                  }
            }
    }
  }
}
