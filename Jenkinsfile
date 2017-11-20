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
               sh 'mvn test'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn verify -Pintegrationtest'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {

        success {
          echo 'success'
        }
        failure {
          echo 'failure'
        }
    }
}