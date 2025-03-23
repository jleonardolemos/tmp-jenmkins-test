pipeline {
    agent {
        docker { image 'convenia/php-full:latest' }
    }
    environment {
        JOKE = credentials('joke')
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
                echo "$JOKE"
                sh 'echo "######################" > ./data.txt'
            }
        }
        stage('Test Jenkinsfile'){
            steps {
                sleep 1
                echo '$JOKE'
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