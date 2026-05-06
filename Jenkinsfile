pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub...'
                checkout scm
            }
        }
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t devops-lab-project:latest .'
            }
        }
        stage('Deploy to K8s') {
            steps {
                echo 'Deploying to Minikube...'
                bat 'kubectl apply -f k8s-deploy.yaml'
            }
        }
    }
}
