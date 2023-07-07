pipeline {
    agent any
    tools { nodejs 'node' }
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/17021084/hello-jenkins.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
    }
}
