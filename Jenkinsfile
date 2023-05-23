pipeline {

    agent {
        label 'my-ssh-agent-2'
    }

    tools {
        nodejs 'nodejs'
    }

    stages {

        stage('Clean') {
            steps {
                cleanWs()
            }
        }

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/TodorM123/nodejs-my-proj'
            }
        }
        stage('Build') {
            steps {
                sh 'npm ci' //This is for building the nodejs project
            }
        }
        stage('Test') {
            steps {
                sh 'npm test' //This is for testing the nodejs modules
            }
        }
        stage('Deploy') {
           steps {
                sh 'pkill node | true'
                sh 'npm install -g forever'
                sh 'forever start src/index.js'
           }
        }
    }
}