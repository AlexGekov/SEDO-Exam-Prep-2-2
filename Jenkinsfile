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
                bad 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                bad 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                bad 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
