pipeline {
  environment {
    registry = "akanshagiriya/demo"
    registryCredential = 'Docker_cred'
  }
  properties([gitLabConnection(gitLabConnection: '', jobCredentialId: ''), parameters([string(defaultValue: 'main', name: 'branch')])])
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git branch: "${params.branch}", url: 'https://github.com/sk-sharif/prac.git'
        sh 'git checkout -b "${params.branch}"'
      }
    }
     stage('Build Unit test') {
      steps{
        echo 'unit tests'
      }
    }
  }
}
