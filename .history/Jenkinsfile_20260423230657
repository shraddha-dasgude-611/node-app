pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/shraddha-dasgude-611/node-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-app:latest .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f node-app-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name node-app-container -p 3000:3000 node-app:latest'
            }
        }
    }
}