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
        stage('Report') {
            parallel {
                stage('PHP Version') {
                    steps {
                        php --version
                    }
                }
                stage('Laravel Version') {
                    steps {
                        php artisan about
                    }
                }
            }
        }
    }
}