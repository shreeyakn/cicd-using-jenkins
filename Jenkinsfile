pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-node-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop node-container || exit 0'
                bat 'docker rm node-container || exit 0'
                bat 'docker run -d -p 3000:3000 --name node-container devops-node-app'
            }
        }

    }
}
