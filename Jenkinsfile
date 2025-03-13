pipeline {
    agent any

    triggers {
        githubPush()  // Triggers build when you push to GitHub
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/belhoutahmed/coachaac.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Mocha Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit '**/test-results.xml'
            }
        }
    }
}
