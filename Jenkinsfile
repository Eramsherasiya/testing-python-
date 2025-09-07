pipeline {
    agent any

    environment {
        DOCKER_HUB_CREDENTIALS = credentials('dockerhub')
        DOCKER_IMAGE = "yourdockerhubusername/webapp:${BUILD_NUMBER}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/YeshaShah13/labwork-4.git'
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
            stage('Push Docker Image') {
                steps {
                    withDockerRegistry([credentialsId: 'dockerhub', url: '']) {
                        sh 'docker push $DOCKER_IMAGE'
                    }
                }
            }
        }
    }
}
