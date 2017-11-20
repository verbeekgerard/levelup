
pipeline {
    agent any

    tools {
        maven'M3'
        jdk 'jdk1.8'
     }
    
    stages {
        stage('Build') {
            steps {
                echo 'sh mvn test'
            }
        }
        stage('Test') {
            steps {
                echo 'mvn verify -Pintegrationtest'
            }
        }
        stage('Deploy') {
            steps {
                retry(3) {
                    echo 'siavash...'
                }

                timeout(time: 3, unit: 'MINUTES') {
                   input message:'Approve deployment?'
                }
            }
        }
    }
     post {
        always {
            echo 'deaskdkas'
        }
        failure {
              echo 'Deploying....'
        }
    }
}
