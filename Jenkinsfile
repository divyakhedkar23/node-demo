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
                echo 'Running npm install...'
                sh 'npm install || echo "No dependencies found."'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
        }

        stage('Run App') {
            steps {
                echo 'Executing Node.js application...'
                sh 'node app.js'
            }
        }
    }

    post {
        success {
            echo '✔ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
