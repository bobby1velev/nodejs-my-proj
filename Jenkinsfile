pipeline {
    agent {
        label 'docker-slave'
    }
    
    tools {
  nodejs 'nodejs'
}
    
    stages {
        stage ('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/bobby1velev/nodejs-my-proj.git'
            }
        }
        stage ('Build') {
            steps {
                sh 'npm ci' //this is a comment
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'forever start src/index.js'
            }
        }
    }
}