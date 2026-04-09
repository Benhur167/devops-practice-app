pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker rm -f devops-app 2>nul
                docker run -d -p 3000:3000 --name devops-app devops-app
                '''
            }
        }
    }
}
