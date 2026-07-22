pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:ashasrivallibanka/docker-practice.git',
                    credentialsId: 'github-ssh'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t task-manager-demo .'
            }
        }
        stage('Verify Image') {
            steps {
                sh 'docker images'
            }
        }
    }
}

