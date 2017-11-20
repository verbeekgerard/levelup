pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        success {
            mail to: gerard.verbeek@luminis.eu, subject: 'The Pipeline failed :('
        }
        failure {
            mail to: gerard.verbeek@luminis.eu, subject: 'The Pipeline failed :('
        }
    }
}