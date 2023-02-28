pipeline {
    agent any
    
    stages {
        stage('SCM CHECKOUT') {
            steps {
                git 'https://github.com/sangajala/hospitalrun-frontend.git'
            }
        }
        stage('Building Node JS') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS') {
                sh "npm install" 
                }
            }
        }
    }
}
