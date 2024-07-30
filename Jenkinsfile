pipeline {
    agent {
        docker {
            image 'node:14'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Build the Docker image
                sh 'docker build -t express-server .'
            }
        }
        stage('Test') {
            steps {
                // Run the Docker container
                sh 'docker run -d -p 3000:3000 --name express-server-test express-server'

                // Optionally, you can run some tests here
                // Example: sh 'docker exec express-server-test npm test'

                // Stop and remove the container
                sh 'docker stop express-server-test'
                sh 'docker rm express-server-test'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy your Docker container
                // This could be to a staging environment or production
                // Example: sh 'docker run -d -p 3000:3000 --name express-server express-server'
            }
        }
    }
}