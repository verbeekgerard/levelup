#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        maven 'M3'
        jdk 'jdk1.8.0'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn test'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        stage('Test') {
            steps {
                sh 'mvn verify -Pintegrationtest'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        input 'Do you approve deployment?'
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
}
