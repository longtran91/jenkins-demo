pipeline {
  agent any
  tools {dockerTool "docker"}
  stages {
    stage('Clone') {
      steps {
        git branch: 'main', url: 'https://github.com/longtran91/jenkins-demo.git'
      }
    }
    stage('Build docker') {
      steps {
        withDockerRegistry(credentialsId: 'docker-demo', url: 'https://index.docker.io/v1/') {
          sh 'docker build -t longtd91/jenkins:v1 .'
          sh 'docker push longtd91/jenkins:v1'
        }
      }
    }
  }
}