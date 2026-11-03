pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'javac Hello.java'
            }
        }

        stage('Test') {
            steps {
                bat 'java Hello'
            }
        }

        stage('Deploy') {
            steps {
                bat 'mkdir deployment'
                bat 'copy Hello.class deployment\\'
                archiveArtifacts artifacts: 'deployment/Hello.class'
            }
        }
    }
}
