#!/usr/bin/env groovy

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Done!"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                echo "Done!"
            }
        }
        stage('Deploy') {
            steps {
                retry(3) {
                    echo 'Deploying....'
                }

                timeout(time: 3, unit: 'MINUTES') {
                    echo "Done health check!"
                }

            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}
