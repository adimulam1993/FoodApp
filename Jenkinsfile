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

        stage('Stop Old Container') {
            steps {
                bat 'docker rm -f foodapp-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name foodapp-container foodapp'
            }
        }
    }
}
