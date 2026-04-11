pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/adimulam1993/FoodApp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t foodapp .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }
    }
}
