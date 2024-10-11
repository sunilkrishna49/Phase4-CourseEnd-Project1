pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
               git branch: 'main', url: 'https://github.com/sunilkrishna49/estore-admin-dashboard.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install --legacy-peer-deps'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Dockerize') {
            steps {
                sh 'docker build -t angular-admin-app .'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:80 angular-admin-app'
            }
        }
    }
}
