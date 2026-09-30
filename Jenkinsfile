pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t devops-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker rm -f devops-container || exit 0'
                bat 'docker run -d --name devops-container devops-app'
            }
        }
    }
}