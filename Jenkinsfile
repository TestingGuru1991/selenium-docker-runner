pipeline {
	agent any
	stage('Run Test') {
            steps {
                bat "docker-compose up"
            }
        }
	stage('Bring Grid Down') {
            steps {
                bat "docker-compose down"
            }
        }
}