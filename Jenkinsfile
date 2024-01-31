pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Your build steps go here
                // For example, if it's a Maven project:
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Your test steps go here
                // For example, if it's a Maven project:
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Your deployment steps go here
                // For example, if you are deploying a Docker image to Harbor:
                sh 'docker build -t your-docker-image .'
                sh 'docker push your-docker-image:latest'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! The application is built, tested, and deployed successfully.'
        }
        failure {
            echo 'Pipeline failed. Check the logs for details.'
        }
    }
}
