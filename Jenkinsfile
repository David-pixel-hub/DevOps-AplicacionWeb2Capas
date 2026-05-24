pipeline{
    agent any
    stages{
        stage('Clone repo'){
            steps{
                git branch: 'main', url: 'https://github.com/David-pixel-hub/DevOps-AplicacionWeb2Capas'
            }
        }
        stage('Build image'){
            steps{
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                sh 'docker compose down || true'
                sh 'docker compose up -d --build'
            }
        }
    }
}