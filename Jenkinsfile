pipeline {
    agent any

    stages {
        stage('stop container'){
            steps {
                sh 'docker compose down'
            }
        }
        stage('start container'){
            steps {
                sh 'docker compose up -d'
            }
        }
        stage('check process'){
            steps {
                'docker ps'
            }
        }
    }
}
