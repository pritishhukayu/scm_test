pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out the code from the Git repository using the "main" branch
                git url: 'https://github.com/pritishhukayu/scm_test.git', branch: 'main'
            }
        }

        // Additional stages for build, test, and deploy go here
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for details.'
        }
    }
}
