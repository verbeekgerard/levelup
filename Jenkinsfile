#!/usr/bin/env groovy

pipeline {
    agent any
    tools {
        maven 'M3ß'
        jdk 'jdk1.8.0'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn install'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        stage('Test') {
            steps {
                sh 'mvn verify -Pintegratietest'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
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
}
