/* groovylint-disable-next-line CompileStatic */
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
                sh 'npm install'
            }
        }
        // stage('Check lints') {
        //     steps {
        //         sh 'yarn run lint'
        //     }
        // }
        // stage('Test app') {
        //     steps {
        //         sh 'yarn run test-cicd'
        //     }
        // }
        // stage('Build App') {
        //     steps {
        //         sh 'yarn run build'
        //     }
        // }
        stage('test aws') {
            steps {
                sh 'aws s3 ls '
            }
        }

        // stage('Upload to s3') {
        //     steps {
        //         s3Upload consoleLogLevel: 'INFO',
        //     dontSetBuildResultOnFailure: false,
        //     dontWaitForConcurrentBuildCompletion: false,
        //     entries: [[
        //         bucket: 'trung-demo-cicd',
        //         excludedFile: '',
        //         flatten: false,
        //         gzipFiles: false,
        //         keepForever: false,
        //         managedArtifacts: false,
        //         noUploadOnFailure: true,
        //         selectedRegion: 'ap-northeast-1',
        //         showDirectlyInBrowser: false,
        //         sourceFile: 'build/*',
        //         storageClass: 'STANDARD',
        //         uploadFromSlave: false,
        //         useServerSideEncryption: false]],
        //         pluginFailureResultConstraint: 'FAILURE', profileName: 'default', userMetadata: []
        //     }
        // }
    }
}
