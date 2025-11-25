pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            agent {
                docker {
                    image 'node:18'
                    args '-u root:root'
                }
            }
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
                sh "docker stop mynodeapp || true"
                sh "docker rm mynodeapp || true"
                sh "docker run -d --name mynodeapp -p 3000:3000 mynodeapp:latest"
            }
        }
    }
}
