pipeline {
    agent {
        docker { image 'convenia/php-full:latest' }
    }
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build Jenkinsfile') {
            steps {
                sleep 2
                echo "Image Builded"
            }
        }
        stage('Test Jenkinsfile'){
            agent { node 'local-shell' }
            steps {
                sleep 1
                echo "Image Tested"
            }
        }
        stage('Deploy Jenkinsfile') {
            steps {
                sleep 1
                echo "Image Deployed"
            }
        }
        stage('Report') {
            parallel {
                stage('PHP Version') {
                    steps {
                        sh 'php --version'
                    }
                }
                stage('Laravel Version') {
                    steps {
                        sh 'uname -a'
                    }
                }
            }
        }
    }
}