
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
                echo 'mvn verify -Pintegrationtest'
                echo 'Testing..'
                sh 'mvn verify -Pintegrationtest'
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
