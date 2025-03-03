pipeline {
    agent any

    environment {
        DOCKER_HUB_USER = 'your-dockerhub-username'
        IMAGE_FRONTEND = "${DOCKER_HUB_USER}/frontend"
        IMAGE_BACKEND = "${DOCKER_HUB_USER}/backend"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/UnpredictablePrashant/learnerReportCS_frontend'
                git branch: 'main', url: 'https://github.com/UnpredictablePrashant/learnerReportCS_backend'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_FRONTEND}:latest ./learnerReportCS_frontend"
                    sh "docker build -t ${IMAGE_BACKEND}:latest ./learnerReportCS_backend"
                }
            }
        }

        stage('Push Docker Images') {
            steps {
                script {
                    sh "echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_HUB_USER} --password-stdin"
                    sh "docker push ${IMAGE_FRONTEND}:latest"
                    sh "docker push ${IMAGE_BACKEND}:latest"
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh "kubectl apply -f backend_deployment.yaml"
                    sh "kubectl apply -f frontend_deployment.yaml"
                    sh "kubectl apply -f mongo_deployment.yaml"
                }
            }
        }
    }
}
