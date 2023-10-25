pipeline {
    agent any
    stages {
        stage('opdracht 5') {
            steps {
                echo "good luck..."
            }
        }
        stage('checkout code') {
            steps {
                git branch: 'main', url: 'https://github.com/EmirKaanOzverPXL/calculator-app-finished'
            }
        }

        stage('install dependencies') {
          steps {
            sh 'npm install'
          }
        }

        stage('unittest') {
          steps {
            sh 'npm run test'
          }
        }
    }
}