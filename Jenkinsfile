@Library('jenkins-shared-libs@master') _

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
        dockerCmd 'version'
        dockerCmd 'build -t mikhaild/hellonode:latest .'
        dockerCmd 'image ls'
      }
    }
  }
}
