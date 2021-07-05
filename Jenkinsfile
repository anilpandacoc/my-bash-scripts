pipeline {
  agent any
  environment {
    myvar = "Outer Block"
  }

  stages {
    stage('Checkout'){
      steps{
        checkout scm
      }
    }
    stage('Build'){
      steps{
        sh "sh my-bash-scripts.sh"
      }
    }
    stage('Post tasks'){
      steps{
        sh "echo Emailing"
      }
    }
    stage(' print Env'){
        environment {
            myvar = "Inner Block"
        }
      steps{
        sh 'echo "my variable is ${myvar}"'
      }
    }
  }
}
