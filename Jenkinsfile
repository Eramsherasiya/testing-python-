pipeline {
    agent {
        docker { 
            image 'python:3.11'   // Use official Python Docker image
            args '-u root:root'   // Run as root to allow pip installs
        }
    }

    environment {
        PIP = 'pip'  // You can call pip via ${PIP}
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Eramsherasiya/testing-python-.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '${PIP} install --upgrade pip'
                sh '${PIP} install -r requirements.txt'
            }
        }

        stage('Run Python App') {
            steps {
                sh 'python main.py'  // Replace main.py with your actual entrypoint
            }
        }
    }

    post {
        success { echo 'Pipeline succeeded!' }
        failure { echo 'Pipeline failed!' }
    }
}
