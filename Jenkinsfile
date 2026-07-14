pipeline {
    agent any

    stages {

        stage('Approval') {
            steps {
                input message: 'Do you want to continue with the deployment?', ok: 'Submit'
            }
        }

        stage('Docker Version Check') {
            steps {
                echo 'Checking Docker version...'
                sh 'docker --version'
            }
        }

        stage('Docker Compose Up') {
            steps {
                echo 'Starting Docker Compose...'
                sh 'docker compose up -d'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}