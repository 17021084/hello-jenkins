pipeline {
    agent any
    tools { nodejs 'node' }
    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/17021084/hello-jenkins.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'yarn install'
            }
        }
        stage('Check lints'){
            steps{
                sh 'yarn run lint'
            }
        }
        stage('Test app') {
            steps {
                sh 'yarn run test-cicd'
            }
        }
        stage('Build App') {
            steps {
                sh 'yarn run build'
            }
        }
    }
}
