pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the GitHub repository
                git credentialsId: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, url{https://github.com/satya918/Assign5.git
                    
                    
        

        stage('Build Service 1') {
            steps {
                dir('service1') {
                    // Build the Docker image for service1
                    sh 'docker build -t satya918/service1:latest .'
                }
            }
        }

        stage('Build Service 2') {
            steps {
                dir('service2') {
                    // Build the Docker image for service2
                    sh 'docker build -t satya918/service2:latest .'
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

        stage('Integration Tests') {
            steps {
                // Assuming you have integration tests defined for the entire application
                // You can run integration tests that interact with both services here
                // This might involve using Docker Compose to spin up the services and perform tests
                // The specifics will depend on your application and testing setup
            }
        }

        stage('Deploy') {
            steps {
                // Assuming you have a Docker Compose file (docker-compose.yml) in the root of your project
                // You can deploy the services using Docker Compose
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
        }
