pipeline{
    agent any
    stages {
        stage('Upload to AWS')  {
            steps {
                withAWS(credentials: 'AKIAZZKH3T3VTGMSHU43 (Static HTML publisher in AWS)', region: 'eu-central-1'){
                    s3Delete(bucket: 'udacity-pipeline-project', path:'**/*')
                    s3Upload(bucket: 'udacity-pipeline-project', workingDir:'build', includePathPattern:'**/*');
                  }
            }
    }
}
