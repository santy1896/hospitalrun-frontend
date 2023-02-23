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
                nodejs(nodeJSInstallationName: 'NodeJS') {
                sh "npm install"    
        } 
            }
           }
        stage('testing nodejs') {
            steps {
                sh "npm test"
         }
        }
    }
 }

  
