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
                sh 'docker build -t my-app1 .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker stop my-app1 || true'
                sh 'docker rm my-app1 || true'
                sh 'docker run -d --name my-app1 -p 80:80 my-app'

            }
        }
    }
}