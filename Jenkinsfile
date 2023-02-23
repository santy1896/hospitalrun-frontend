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
        stages {
        stage('Install Nginx') {
            steps {
                sh 'sudo apt-get update -y'
                sh 'sudo apt-get install -y nginx'
            }
        }
        
        stage('Verify Nginx installation') {
            steps {
                sh 'nginx -v'
            }
        }
        }
    }
 }

  
