pipeline{
    agent any
    tools {
        nodejs 'NodeJS'
    }
    stages{
                stage('Environment'){
            steps{
                sh 'node --version'
                sh 'npm --version'
            }
        }
        stage('Checkout'){
            steps{
                git branch: 'main',
                url: 'https://github.com/Julie-lou/jenkins-node-app.git'
            }
        }
        stage('Install Dependencies'){
            steps{
                sh 'npm ci'
            }
        }
        stage('Test'){
            steps{
                sh 'npm test'
            }
        }
        stage('Build'){
            steps{
                sh 'npm run build'
            }
        }
    }
            post {
            success {
                echo 'Pipeline successful!'
            }
            failure {
                echo 'Pipelain failed!'
            }
        }
}