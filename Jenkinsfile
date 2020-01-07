pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        script {
          sh '''
            sudo docker version
            sudo docker build -t ealebed/hellonode:latest .
            sudo docker image ls
          '''
        }
      }
    }
  }
}
