pipeline {
    agent any
    tools {
        gradle 8.4
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh 'gradle assemble'
            }
        }
         stage('Test') {
            steps {
                sh 'gradle test'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'gradle docker'
            }
        }
        stage('Run Docker Image') {
            steps {
                sh 'gradle dockerRun'
            }
        }
    }
}
