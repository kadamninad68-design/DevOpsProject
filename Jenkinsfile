pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t node-docker-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f node-app'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 3000:3000 --name node-app node-docker-app'
            }
        }
    }
}