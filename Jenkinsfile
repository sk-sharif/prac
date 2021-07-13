pipeline {
  environment {
    registry = "akanshagiriya/demo"
    registryCredential = 'Docker_cred'
  }
//  properties([gitLabConnection(gitLabConnection: '', jobCredentialId: ''), parameters([string(defaultValue: 'main', name: 'branch')])])
//   options([
//     parameters([
//       string(name: 'one', defaultValue: 'main'),
//     ])
//   ])
  agent any
//   stages {
//     stage('Cloning Git') {
//       steps {
//         git branch: "${params.one}", url: 'https://github.com/sk-sharif/prac.git'
//         sh 'git checkout -b "${params.one}"'
//       }
//     }
//      stage('Build Unit test') {
//       steps{
//         echo 'unit tests'
//       }
//     }
//   }
  
    stages {
        stage('Triggering the main job') {
            steps {
                build job: "main/${BRANCH_NAME.replace('/', '%2F')}", 
                      parameters: [string(name: 'RUN_TESTS', value: 'true')]
            }
        }
    }
  
  
}
