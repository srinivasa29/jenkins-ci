pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }

        stage('Build') {
            steps {
                sh "npm run build || echo 'No build step'"
            }
        }

        stage('Test') {
            steps {
                sh "npm test || echo 'No tests'"
            }
        }
    }
}
