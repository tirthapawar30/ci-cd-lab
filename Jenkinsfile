pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                sh 'mkdir -p public'
                sh 'cp src/index.html public/'
                sh 'cp src/style.css public/'
                sh 'cp src/calculator.js public/'
                echo 'Calculator files prepared for local deployment'
            }
        }
    }
}