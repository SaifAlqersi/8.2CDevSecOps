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
    }
}
