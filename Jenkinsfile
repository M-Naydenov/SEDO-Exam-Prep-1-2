pipeline {
    agent any
    stages {

        stage('Restore Dependencies') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'Restoring dependencies...'
                bat 'dotnet restore'
            }
        }
        stage('Dotnet build') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'Building...'
                bat 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                echo 'Testing...'
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}