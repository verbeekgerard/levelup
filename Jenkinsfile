@Library('sharedlib') _
pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh(libraryResource('list.sh'))
            }
        }
    }
}
