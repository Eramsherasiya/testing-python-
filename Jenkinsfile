pipeline {
    agent any

    stages {
        stage('Install requirements') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run Python script') {
            steps {
                sh 'python3 your_script.py'
            }
        }
    }
}
