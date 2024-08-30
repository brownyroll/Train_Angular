pipeline {
    agent any

    stages {
        stage('clone project'){
            steps {
                git branch: 'main' , credentialsId: 'Github_Angular', url: 'https://github.com/brownyroll/Train_Angular.git'
            }
        }
        stage('qualityGate'){
            steps {
                sh 'docker run --rm --network Jenkins -v "C:/jenkins-test/jenkins_home/workspace/sonarpipeline:/usr/src" sonarsource/sonar-scanner-cli sonar-scanner'
            }
        }
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
