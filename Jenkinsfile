pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image...."
            }
        }
        stage('deploy-dev') {
            steps {
                echo "Deployment triggered on DEV env...."
            }
        }
        stage('test-dev') {
            steps {
                echo "API tests triggered on DEV env...."
            }
        }
        stage('deploy-stg') {
            steps {
                echo "Deployment triggered on STG env...."
            }
        }
        stage('test-stg') {
            steps {
                echo "API tests triggered on STG env...."
            }
        }
        stage('deploy-prd') {
            steps {
                echo "Deployment triggered on PRD env...."
            }
        }
        stage('test-prd') {
            steps {
                echo "API tests triggered on PRD env...."
            }
        }
    }
}