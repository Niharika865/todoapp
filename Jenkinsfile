pipeline {
    agent any

    stages {

        stage('Check Docker Version') {
            steps {
                echo 'Checking Docker version...'
                sh 'docker --version'
            }
        }

        stage('Docker Compose Up') {
            steps {
                echo 'Starting application using Docker Compose...'
                sh 'docker compose up -d'
            }
        }

    }

    post {
        success {
            echo 'Pipeline executed successfully.'
        }

        failure {
            echo 'Pipeline execution failed.'
        }

        always {
            echo 'Pipeline finished.'
        }
    }
}