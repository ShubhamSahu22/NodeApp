pipeline {
    agent any

    tools {
        nodejs 'NodeJS'
    }

    stages {
        stage('Clone GitHub Repository') {
            steps {
                git branch: 'main', credentialsId: 'git-jenkins-node', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
            }
        }

        stage('Install Node.js Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Test Cases') {
            steps {
                sh 'npm test'
            }
        }
    }
}

