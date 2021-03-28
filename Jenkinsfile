pipeline {
  environment {
    registry = “janerands/achistar”
    registryCredential = ‘DockerCred’
    dockerImage = ‘’
  }
  agent any
  stages {
    stage(‘Cloning Git’) {
      steps {
        git ‘https://github.com/JaneRands/AchiStarTechApp.git'
      }
    }
    stage(‘Building image’) {
      steps{
        script {
          dockerImage = docker.build registry + “:$BUILD_NUMBER”
        }
      }
    }
    stage(‘Deploy Image’) {
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
