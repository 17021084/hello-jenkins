/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools { nodejs 'node' }
    environment {
        S3_BUCKET_NAME = "trung-demo-cicd"
    }

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/17021084/hello-jenkins.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                // sh 'rm package-lock.json'
                sh 'npm install'
            }
        }
        stage('Check lints') {
            steps {
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
        stage ("upload s3 via command"){
            steps {
                sh " aws s3 rm s3://${env.S3_BUCKET_NAME} --recursive"
                sh " aws s3 cp --recursive ./build s3://${env.S3_BUCKET_NAME} "
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
