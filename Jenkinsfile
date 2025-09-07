pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('dockerhub')
        DOCKER_IMAGE = "eramsherasiya/webapp:${BUILD_NUMBER}"  // replace with your Docker Hub username
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Eramsherasiya/testing-python-.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Test Docker Image') {
            steps {
                sh 'docker run --rm $DOCKER_IMAGE echo "Image built successfully!"'
            }
        }
    }

    post {
        success {
            withDockerRegistry([credentialsId: 'dockerhub', url: '']) {
                sh 'docker push $DOCKER_IMAGE'
            }
        }
    }
}
