pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t python-app .'
            }
        }

        stage('Run Tests Inside Docker') {
            steps {
                bat 'docker run --rm python-app pytest'
            }
        }

        stage('Run Application') {
            steps {
                bat 'docker run --rm python-app'
            }
        }
    }
}
