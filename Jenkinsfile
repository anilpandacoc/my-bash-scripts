pipeline {
  agent any
  environment {
    myvar = "Outer Block"
  }

  stages {
    stage('Checkout'){
      steps{
        git branch: 'main', credentialsId: 'anilgithub', url: 'https://github.com/anilpandacoc/my-bash-scripts.git'
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
