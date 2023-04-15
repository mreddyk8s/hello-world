pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                sh 'echo Hello Build stage'
            }
        }
        stage ('Test') {
            steps {
                sh 'echo hello Test stage'
            }
        }
        stage ('Scan and Build Jar File') {
            steps {
               withSonarQubeEnv(installationName: 'Production SonarQubeScanner', credentialsId: 'SonarQubeToken') {
                sh 'mvn clean package sonar:sonar'
            }
        }
    }
}
