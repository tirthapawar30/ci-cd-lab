pipeline {
    agent any

    environment {
        PATH = "/usr/local/bin:/opt/homebrew/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'node -v'
                sh 'npm -v'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
    when {
        branch 'main'
    }
    steps {
        sh 'mkdir -p /Users/Shared/ci-cd-deploy'
        sh 'cp src/index.html /Users/Shared/ci-cd-deploy/'
        sh 'cp src/style.css /Users/Shared/ci-cd-deploy/'
        sh 'cp src/calculator.js /Users/Shared/ci-cd-deploy/'
        echo 'Application deployed to /Users/Shared/ci-cd-deploy'
    }
}
    }
}