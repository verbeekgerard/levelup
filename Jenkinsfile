
pipeline {
    agent any

    tools {
        maven 'M3'
        jdk 'jdk1.8.0'
     }
    
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
    }
     post {
        always {
            junit '**/target/*.xml'
        }
        failure {
              echo 'Deploying....'
        }
    }
}
