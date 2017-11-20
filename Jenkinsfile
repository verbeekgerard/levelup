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

                 retry(3) {
                    echo 'smoke....'
                 }

                 timeout(time: 3, unit: 'MINUTES') {
                    echo 'Timeout!'
                 }

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