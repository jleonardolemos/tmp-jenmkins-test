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
                sh 'pwd'
                sh 'echo "######################" > ./data.txt'
            }
        }
        stage('Test Jenkinsfile'){
            steps {
                sleep 1
                echo "Image Tested"
                sh 'pwd'
                sh 'cat ./data.txt'
            }
        }
        stage('Deploy Jenkinsfile') {
            agent { node 'local-shell' }
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