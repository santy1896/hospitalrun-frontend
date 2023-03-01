pipeline {														
    agent any
    
    stages {
        stage('SCM CHECKOUT') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/sangajala/hospitalrun-frontend.git']]])
            }
        }
        stage('Building Node JS') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS 12.22.11') {
                sh "npm install"
            }
          }
        }      
        stage("Starting the Application") {
            steps {
                sh "npm start"
            }             
        }  
     }    
 }
