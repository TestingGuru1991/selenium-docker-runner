pipeline {
    agent any
    stages {
        stage('Pull Latest Image') {
            steps {
                bat "docker pull petar123123123/selenium-docker"
            }
        }
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