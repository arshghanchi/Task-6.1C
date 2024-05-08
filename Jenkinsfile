pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Performing build using Maven'
                echo 'Maven is a build automation tool used to compile, package, and manage dependencies for Java projects.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using JUnit'
                echo 'Running integration tests using TestNG'
                echo 'JUnit and TestNG are popular testing frameworks for Java applications.'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis using SonarQube'
                echo 'SonarQube is a code quality and security scanning tool that helps identify code smells, bugs, and vulnerabilities.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Performing security scan using OWASP ZAP'
                echo 'OWASP ZAP (Zed Attack Proxy) is a free and open-source web application security scanner.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging environment (e.g., AWS EC2 instance)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production environment (e.g., AWS EC2 instance)'
            }
        }
    }

    post {
        success {
            mail to: 'arsh.ghanchi07@gmail.com',
                 subject: "Pipeline '${currentBuild.fullDisplayName}' succeeded",
                 body: "The pipeline '${currentBuild.fullDisplayName}' completed successfully."
        }
        failure {
            mail to: 'arsh.ghanchi07@gmail.com',
                 subject: "Pipeline '${currentBuild.fullDisplayName}' failed",
                 body: "The pipeline '${currentBuild.fullDisplayName}' failed. Please check the logs.",
                 attachLog: true
        }
    }
}
