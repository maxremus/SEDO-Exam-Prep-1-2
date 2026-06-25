pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test'
            }
        }
    }

    post {
        success {
            echo "SUCCESS: .NET build and tests passed on ${env.BRANCH_NAME}"
        }

        failure {
            echo "FAILED: .NET build or tests failed"
        }
    }
}
