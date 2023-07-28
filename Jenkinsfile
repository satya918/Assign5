pipeline {
    agent any // Or specify the agent label/nodes where the pipeline should run

    stages {
        stage('Build Service 1') {
            steps {
                dir('service1') {
                    // Build the Docker image for service1
                    sh 'sudo docker build -t satya918/service1:latest .'
}
            }
        }

        stage('Build Service 2') {
            steps {
                dir('service2') {
                    // Build the Docker image for service2
                    sh 'sudo docker build -t satya918/service2:latest .'
                }
            }
        }

        stage('Unit Tests') {
            steps {
                dir('service1') {
                    // Run unit tests for service1
                    sh 'npm test'
                }

                dir('service2') {
                    // Run unit tests for service2
                    sh 'pytest'
                }
            }
        }

       

        stage('Deploy') {
            steps {
                    sh 'docker-compose up -d'
            }
        }
    }
 post {
        success {
            echo 'CI/CD process completed successfully!'
        }
        failure {
            echo 'CI/CD process failed!'
        }
    }
    }

