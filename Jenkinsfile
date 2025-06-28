pipeline {
    agent any

    // Optional: Trigger on develop/feature branch push (Jenkins needs to be configured for branch filtering)
    triggers {
        pollSCM('* * * * *') // Adjust or remove as needed. Webhooks are preferred.
    }

    stages {
        stage('Checkout the repo') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
