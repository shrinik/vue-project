pipeline {
    agent any 
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main',
                        url: 'https://github.com/shrinik/vue-project.git'
                }
            }
        }        
        stage('Install') { 
            steps {
                nodejs(nodeJSInstallationName: 'node') {
                    sh 'npm install'
                }
            }
        }
        stage('Lint') { 
            steps {
                nodejs(nodeJSInstallationName: 'node') {
                    sh 'npm run lint'
                }
            }
        }
        stage('Test') { 
            steps {
                nodejs(nodeJSInstallationName: 'node') {
                    sh 'npm run test'
                }
            }
        }
        stage('Build') { 
            steps {
                nodejs(nodeJSInstallationName: 'node') {
                    sh 'npm run build'
                }
            }
        }        
    }
}