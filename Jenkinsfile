pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker build -t simple-webapp-flask:latest .'
                sh 'docker run -d -p 5000:5000 simple-webapp-flask:latest'
            }
        }
    }
}
