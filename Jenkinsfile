pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout successful'
            }
        }

        stage('Deploy to S3') {
            steps {
                sh '''
                  aws s3 sync . s3://jenkins-s3-demo-mahes-001 \
                  --delete \
                  --exclude ".git/*" \
                  --exclude "Jenkinsfile"
                '''
            }
        }
    }
}
