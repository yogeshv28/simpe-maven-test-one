pipeline {
    agent any
    triggers {
        cron('*/2 * * * *')
    }
    parameters {
        string(name: 'DEPLOY_ENV', defaultValue: 'dev', description: '')
    }
    stages {
        stage('SCA') {
            steps {
                echo 'Steps to perform Static Code Analysis'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Steps to execute Unit Tests'
            }
        }
        stage('Build') {
            steps {
                echo 'Steps to execute build commands'
            }
        }
        stage('Docker Image') {
            steps {
                echo 'Steps to create Docker Image'
            }
        }
        stage('Scan Docker Image') {
            options {
                skipDefaultCheckout()
            }
            steps {
                echo 'Steps to Scan Docker Image'
            }
        }
        stage('Deploy to Minikube') {
            steps {
                echo "Steps to deploy application to ${params.DEPLOY_ENV} minikube cluster"
            }
        }        
    }
    post {
        always {
            echo "Steps to publish Unit Tests results"
        }
    }
}
