pipeline {
    agent any

    environment {
        PIP = 'pip3'   // Use pip3 on the Jenkins server
        PYTHON = 'python3'
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
                sh '${PYTHON} main.py'   // Replace main.py with your script
            }
        }
    }

    post {
        success { echo 'Pipeline succeeded!' }
        failure { echo 'Pipeline failed!' }
    }
}
