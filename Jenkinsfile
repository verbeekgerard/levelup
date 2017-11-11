@Library('sharedlib') _
pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                debug {
                    
                }
            }
        }
        stage('Compile') {
            steps {
                sh(libraryResource('list.sh'))
            }
        }
    }
}
