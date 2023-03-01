pipeline {
    agent any
    
    stages {
        stage('SCM CHECKOUT') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/sangajala/hospitalrun-frontend.git']]])
            }
            }
        }
        stage('Building Node JS') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS 12.22.11') {
                sh "npm install"
            }

        stage('Build Docker Image')  {
            sh 'docker build -t hospitalrun-frontend_couchdb .'
            }     
         }
        stage('docker deployment') {
            sh 'docker run -d -p 8080:8090 --name nginx hospitalrun-frontend_couchdb'

        }
    }
            
 }
