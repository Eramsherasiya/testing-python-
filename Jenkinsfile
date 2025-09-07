pipeline {
    agent {
        docker {
            image 'jenkins-python:latest'
        }
    }
    stages {
        stage('Install requirements') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run Python') {
            steps {
                sh 'python3 your_script.py'
            }
        }
    }
}
