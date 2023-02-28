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
                nodejs(nodeJSInstallationName: 'NodeJS 10.19.0') {
                sh "npm install" 
                }
            }
        }
    }
}
