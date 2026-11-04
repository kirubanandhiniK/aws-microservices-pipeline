pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub repository...'
                checkout scm
            }
        }

        stage('Build & Test: User Service') {
            steps {
                echo 'Building User Service...'
                dir('user-service') {
                    // Add your build commands here (e.g., npm install, mvn clean package, etc.)
                    echo 'User Service build completed successfully.'
                }
            }
        }

        stage('Build & Test: Product Service') {
            steps {
                echo 'Building Product Service...'
                dir('product-service') {
                    // Add your build commands here
                    echo 'Product Service build completed successfully.'
                }
            }
        }

        stage('Build & Test: Order Service') {
            steps {
                echo 'Building Order Service...'
                dir('order-service') {
                    // Add your build commands here
                    echo 'Order Service build completed successfully.'
                }
            }
        }

        stage('Deploy to AWS EC2') {
            steps {
                echo 'Deploying microservices to AWS EC2 Instance (107.22.82.79)...'
                // Add deployment steps or scripts here
                echo 'Deployment completed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully for all microservices!'
        }
        failure {
            echo 'Pipeline failed! Please check the logs.'
        }
    }
}
