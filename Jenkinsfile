pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/lilisrv/projet.git'
            }
        }
        stage('Build Angular') {
            steps {
                dir('angular-app') {
                    sh 'docker build -t angular-app .'
                }
            }
        }
        stage('Build Spring Boot') {
            steps {
                dir('springboot') {
                    sh 'docker build -t springboot-app .'
                }
            }
        }
        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}

