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
                library 'levelup'.mavenUnitTest()
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        stage('Integratie Test') {
            steps {
                sh 'mvn verify -Pintegrationtest'
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        stage('Deploy') {
            steps {
                timeout(time:5, unit:'DAYS') {
                    input message:'Approve deployment?'
                }
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
