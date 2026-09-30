pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code checkout completed'
            }
        }

        stage('Backend Install & Test') {
            steps {
                dir('backend') {
                    bat 'npm ci'
                    bat 'npm test'
                }
            }
        }

        stage('Frontend Install & Build') {
            steps {
                dir('frontend') {
                    bat 'npm ci'
                    bat 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'Nutriflow CI pipeline completed successfully!'
        }

        failure {
            echo 'Nutriflow CI pipeline failed.'
        }
    }
}