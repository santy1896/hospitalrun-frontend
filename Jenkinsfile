pipeline {
    agent any
    
    stages {
        stage('SCM CHECKOUT') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/sangajala/hospitalrun-frontend.git']]])
            
            }
        }
        stage('Build') {
            steps {
             sh 'npm install'
             sh '<<Build Command>>'
            }
        }
    }
            
 }
