pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build Jenkinsfile') {
            steps {
                sleep 20
                echo "Image Builded"
            }
        }
        stage('Test Jenkinsfile'){
            steps {
                sleep 10
                echo "Image Tested"
            }
        }
        stage('Deploy Jenkinsfile') {
            steps {
                sleep 10
                echo "Image Deployed"
            }
        }
    }
}