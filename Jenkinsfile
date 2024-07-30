pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    checkout scm

                    sh 'docker build -t express-server .'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Run the Docker container
                    sh 'docker run -d -p -p 5000:5000 user-express-server'

                    sh 'docker stop express-server-test'
                    sh 'docker rm express-server-test'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    
                }
            }
        }
    }
}