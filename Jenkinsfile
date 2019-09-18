pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                '''
                withAWS(region:'eu-west-1', credentials:'aws-static') {
                    s3Upload(file:'index.html', bucket:'static-udacity', path:'index.html')
                }
            }
            
        }
    }
}
