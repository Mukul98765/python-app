pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "python-app:latest"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Mukul98765/python-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}

