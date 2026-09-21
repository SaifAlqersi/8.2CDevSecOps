pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Security Audit') {
            steps {
                bat 'npm audit || exit /b 0'
            }
        }

        stage('Snyk Security Scan') {
            steps {
                withCredentials([string(credentialsId: 'snyk-token', variable: 'SNYK_TOKEN')]) {
                    bat 'npx snyk test || exit /b 0'
                }
            }
        }
    }
}
