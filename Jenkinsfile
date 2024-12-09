pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-docker-image') {
            steps {
                build()
            }
        }
        stage('deploy-dev') {
            steps {
                deploy("DEV")
            }
        }
        stage('test-dev') {
            steps {
                run-api-tests("DEV")
            }
        }
        stage('deploy-stg') {
            steps {
                deploy("STG")
            }
        }
        stage('test-stg') {
            steps {
                run-api-tests("STG")
            }
        }
        stage('deploy-prd') {
            steps {
                deploy("PRD")
            }
        }
        stage('test-prd') {
            steps {
                run-api-tests("PRD")
            }
        }
    }
}
def build(){
    echo "Building docker image....."
}

def deploy(String environment){
    echo "Deployment triggered on ${environment} env...."
}

def run_api_tests(String environment){
    echo "API tests triggered on ${environment} env...."
}