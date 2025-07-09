pipline{
  agent any

  stages{
    stages('Build') {
      steps{
        echo 'Building...'
      }
    }

     stages('Test') {
      steps{
        sh 'python --version'
      }
    }


     stages('Deploy') {
      steps{
        echo 'Deploying...'
      }
    }
  }
}
