pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-node-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop node-container || true'
                sh 'docker rm node-container || true'
                sh 'docker run -d -p 3000:3000 --name node-container devops-node-app'
            }
        }

    }
}
