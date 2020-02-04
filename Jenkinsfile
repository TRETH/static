pipeline{
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS')  {
            steps {
                withAWS(credentials: 'aws-static', region: 'eu-central-1'){
                    s3Upload(bucket: 'udacity-pipeline-project', pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html');
                  }
            }
        }
    }
}