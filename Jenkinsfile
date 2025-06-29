pipeline {
    agent any

    stages {
        stage('Checkout the repo') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build repo') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test repo') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}