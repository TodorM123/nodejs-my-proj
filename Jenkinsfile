pipeline {

    agent {
        label 'group1'
    }

    tools {
        nodejs 'nodejs'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/stoenpav/nodejs-my-proj.git'
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
                sh 'npm install -g forever'
                sh 'forever start src/index.js'
           }
        }
    }
}
