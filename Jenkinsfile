pipeline {
    agent any

    environment {
        TESTING_ENVIRONMENT = "stage"
        PRODUCTION_ENVIRONMENT = "farhan"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Using Maven for automated builds"
                    echo "Using a build automation tool to compile and package the code"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Using JUnit for automated unit tests"
                    echo "Running unit tests"
                    // Replace [Tool Name] with the actual tool name for integration tests
                    echo "Using [Tool Name] for integration tests"
                    echo "Running integration tests"
                }
            }
            post {
                success {
                    emailext(
                        subject: "Test Stage - Success",
                        body: "The test stage has completed successfully.",
                        to: "harrylying.21@gmail.com",
                    )
                }
                failure {
                    emailext(
                        subject: "Test Stage - Failure",
                        body: "The test stage has failed. Please investigate.",
                        to: "harrylying.21@gmail.com",
                    )
                }
            }
        }

        stage('Code Quality Check') {
            steps {
                script {
                    echo "Using SonarQube for code quality checks"
                    echo "Checking the quality of the code"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Using AWS CodeDeploy for deployment"
                    echo "Deploying the application to the testing environment: $TESTING_ENVIRONMENT"
                }
            }
        }

        stage('Approval') {
            steps {
                script {
                    echo "Waiting for manual approval..."
                    sleep(time: 10, unit: 'SECONDS')
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                script {
                    echo "Using Kubernetes for production deployment"
                    echo "Deploying the code to the production environment: $PRODUCTION_ENVIRONMENT"
                }
            }
        }
    }
}
