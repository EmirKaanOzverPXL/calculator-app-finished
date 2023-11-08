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
            junit "junit.xml"
          }
        }

        stage('create bundle') {
          steps {
            sh 'mkdir bundle'
            sh 'cp -r node_modules bundle'
            sh 'cp -r public bundle'
            sh 'cp *.js* bundle'
            sh 'cp Dockerfile bundle'
            sh 'cp docker-compose.yml bundle'
          }
        }
    }

    post {
      success {
        steps{
          sh 'mkdir artifacts'
          archiveArtifacts 'artifacts/*'
        }
      }

      failure {
        steps {
          // sh 'echo "pipeline poging faalt op" >> "/var/lib/jenkins/jenkinserrorlog"'
          // sh 'echo date +%A' '%d' '%B' '%T >> "/var/lib/jenkins/jenkinserrorlog"']
          echo "failed"
        }
      }
    }
}