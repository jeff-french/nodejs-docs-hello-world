pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                nodejs('node-10-lts') {
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                nodejs('node-10-lts') {
                    sh 'npm test'
                }
            }
        }
        stage('Package Artifacts') {
            steps {
                archiveArtifacts artifacts: '*', excludes: '.git/', fingerprint: true, onlyIfSuccessful: true
            }
        }
    }
}
