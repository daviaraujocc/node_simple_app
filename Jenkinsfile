pipeline {
    agent any

    tools {nodejs "node12"}
    
   environment {
       
    registry = "david13356"
    registryCredential = '473db8fb-7b36-4c66-aa81-1e38faa4afdc'
    dockerImage_api = ''
    dockerImage_web = ''
    
   }
  
    stages {
        stage('Clone Git') {
             steps {
                 git(credentialsId: '1bd4fb12-1bd4-4f3f-b155-7764792770ab', url: 'https://github.com/DaviAraujoCC/node_simple_app', branch: 'main')
             }
        }
        stage('Install dependecies') {
            steps {
              dir ('src/api') {
                bat "npm install"
              }
              dir ('src/web') {
                bat "npm install"  
              }
            }
        }
        stage('Build app') {
            steps {
              dir ('src/web') {
                bat 'npm build'
              }
              dir ('src/api') {
                bat 'npm build'
              }
            }
        }
        stage('Build Image') {
            steps {
              dir ('src/web') {
                script {
                     docker.build registry + ":$BUILD_NUMBER"
                     dockerImage_web = docker.build registry + ":$BUILD_NUMBER"
                }
              }
              dir ('src/api') {
                script {
                     docker.build registry + ":$BUILD_NUMBER"
                     dockerImage_api = docker.build registry + ":$BUILD_NUMBER"
                }
              }
            }
        }
        stage('Deploy the Image') {
            steps {
              script {
                 docker.withRegistry( '', registryCredential ) {
                 dockerImage_web.push()
                 dockerImage_api.push()
                }
              }
            }
        }
    }
}
