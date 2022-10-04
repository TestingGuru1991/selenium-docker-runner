pipeline {
    agent any
    stages {
        stage('Start Grid') {
            steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Running Test') {
            steps {
                bat "docker-compose up search-module book-flight-module"
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'output/**'
            bat "docker-compose down"
        }
    }
}