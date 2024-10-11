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
                bat 'npm install --legacy-peer-deps'  // Use 'bat' for Windows
            }
        }
        stage('Build') {
            steps {
                bat 'npm run build'  // Use 'bat' for Windows
            }
        }
        stage('Dockerize') {
            steps {
                bat 'docker build -t angular-admin-app .'  // Use 'bat' for Windows
            }
        }
        stage('Deploy') {
            steps {
                bat 'docker run -d -p 80:80 angular-admin-app'  // Use 'bat' for Windows
            }
        }
    }
}
