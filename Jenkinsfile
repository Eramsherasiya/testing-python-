pipeline {
    agent any

    environment {
        PYTHON = "python3"
    }

    stage('Checkout Code') {
    steps {
        git branch: 'main', url: 'https://github.com/Eramsherasiya/testing-python-.git'
    }
}


        stage('Install Dependencies') {
            steps {
                // If you have a requirements.txt
                sh 'if [ -f requirements.txt ]; then $PYTHON -m pip install --user -r requirements.txt; fi'
            }
        }

        stage('Run Python App') {
            steps {
                // Replace app.py with your main script
                sh '$PYTHON app.py'
            }
        }

        stage('Success') {
            steps {
                echo 'Pipeline completed successfully!'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
