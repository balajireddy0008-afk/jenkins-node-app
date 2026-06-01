    pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-node-app:v1 .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f nodeapp || true
                docker run -d --name nodeapp -p 3000:3000 jenkins-node-app:v1
                '''
            }
        }
    }
}   
