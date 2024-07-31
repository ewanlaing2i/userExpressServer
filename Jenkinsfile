pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/ewanlaing2i/userExpressServer'
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'npm start'
            }
        }
    }
}