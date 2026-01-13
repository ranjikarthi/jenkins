pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/ranjikarthi/jenkins.git'
            }
        }

        stage('Check Python') {
            steps {
                sh 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app:1.0 .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run --rm python-app:1.0'
            }
        }
    }
}
