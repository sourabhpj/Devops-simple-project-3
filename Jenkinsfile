pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                    checkout scm
                }
                }

        stage('Build') {
            steps {
                sh 'docker build -t my-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop my-app || true'
                sh 'docker rm my-app || true'
                sh 'docker run -d --name my-app -p 80:80 my-app'

            }
        }
    }
}