pipeline {
    agent any

    environment {
        APP_ENV = 'staging'
    }

    stages {

        stage('Build') {
            steps {
                retry(3) {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    try {
                        sh 'npm test'
                    } catch (err) {
                        currentBuild.result = 'UNSTABLE'
                    }
                }
            }
        }
    }
}
