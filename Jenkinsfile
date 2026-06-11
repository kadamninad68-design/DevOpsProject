pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t mobile-shop .'
            }
        }

        stage('Remove Old Container') {
            steps {
                bat 'docker rm -f mobile-shop-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name mobile-shop-container mobile-shop'
            }
        }
    }
}