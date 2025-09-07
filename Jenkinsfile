pipeline {
    agent any

    environment {
        PYTHON = 'python3'
        PIP = 'pip3'
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout main branch explicitly
                git branch: 'main', url: 'https://github.com/Eramsherasiya/testing-python-.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '${PIP} install -r requirements.txt'
            }
        }

        stage('Run Python App') {
            steps {
                sh '${PYTHON} main.py'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
