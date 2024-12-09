pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-docker-image') {
            steps {
                buildImage()
            }
        }
        stage('deploy-dev') {
            steps {
                deploy("DEV")
            }
        }
        stage('test-dev') {
            steps {
                runApiTests("DEV")
            }
        }
        stage('deploy-stg') {
            steps {
                deploy("STG")
            }
        }
        stage('test-stg') {
            steps {
                runApiTests("STG")
            }
        }
        stage('deploy-prd') {
            steps {
                deploy("PRD")
            }
        }
        stage('test-prd') {
            steps {
                runApiTests("PRD")
            }
        }
    }
}
def buildImage(){
    echo "Building docker image....."
    sh 'which docker'
    sh 'docker --version'
    sh 'docker build -t kristinaaraja/sample-book-app .'

    echo "Pushing image for docker registry.."
    sh 'docker push kristinaaraja/sample-book-app'
}

def deploy(String environment){
    echo "Deployment triggered on ${environment} env...."
}

def runApiTests(String environment){
    echo "API tests triggered on ${environment} env...."
}