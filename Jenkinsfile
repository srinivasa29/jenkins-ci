pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t mynodeapp:latest ."
            }
        }

        stage('Run Container') {
            steps {
                sh "docker run -d --name mynodeapp -p 3000:3000 mynodeapp:latest"
            }
        }
    }
}
