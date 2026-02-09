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
                script {
                    def envValue = readFile('idp-input.yaml')
                        .split('\n')
                        .find { it.startsWith('environment:') }
                        .split(':')[1]
                        .trim()

                    if (envValue == 'dev') {
                        echo "Deploying application to DEV environment"
                    } else if (envValue == 'test') {
                        echo "Deploying application to TEST environment"
                    } else if (envValue == 'prod') {
                        echo "Deploying application to PROD environment (with stricter controls)"
                    } else {
                        echo "Unknown environment"
                    }
                }
            }
        }
    }
}
