pipeline {
    agent any

    stages {

        stage('Read IDP Request') {
            steps {
                echo "Reading developer request from IDP (YAML file)"
                bat 'type idp-input.yaml'
            }
        }

        stage('Build Application') {
            steps {
                echo "Building application based on app_type"
            }
        }

        stage('Deploy Application') {
            steps {
                echo "Deploying application to environment"
            }
        }
    }
}
