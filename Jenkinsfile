pipeline {
  environment {
    registry = 'janerands/achistar'
    registryCredential = 'DockerCred'
    dockerImage = ''
  }
  agent any
  stages {
    stage(‘CloneGit’) {
      steps {
        git 'https://github.com/JaneRands/AchiStarTechApp.git'
      }
    }
    stage(‘BuildImage’) {
      steps{
        script {
          dockerImage = docker.build registry + ":${env.BUILD_NUMBER}"
        }
      }
    }
    stage(‘DeployImage’) {
      steps{
        script {
          docker.withRegistry( ‘’, registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }
  }
}
