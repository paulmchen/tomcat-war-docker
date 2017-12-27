#!/usr/bin/env groovy

pipeline {
    agent { docker 'maven:3.3.3' }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                echo 'Building ...'
                sh 'mvn package'
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
        stage('test') {
            steps {
                echo 'Testing ...'
                sh 'mvn test'
            }
        }
   
    }
}
