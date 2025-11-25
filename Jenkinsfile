pipeline {
    agent {
        docker {
            image 'node:18'
            args '-u root:root'  
        }
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mynodeapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name node-app mynodeapp:latest'
            }
        }
    }
}
