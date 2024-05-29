pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                // Maven build command (if applicable)
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Build Stage Passed",
                         body: "The build stage has completed successfully.", attachLog:true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Build Stage Failed",
                         body: "The build stage has failed.", attachLog: true
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                // Unit test command (e.g., mvn test)
                echo 'Running integration tests...'
                // Integration test command (e.g., mvn integration-test)
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Unit and Integration Tests Passed",
                         body: "The unit and integration tests have passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Unit and Integration Tests Failed",
                         body: "The unit and integration tests have failed.", attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
                // SonarQube analysis command
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Code Analysis Passed",
                         body: "The code analysis has passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Code Analysis Failed",
                         body: "The code analysis has failed.", attachLog: true
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning code for security vulnerabilities...'
                // OWASP Dependency-Check command
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Security Scan Passed",
                         body: "The security scan has passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Security Scan Failed",
                         body: "The security scan has failed.", attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server...'
                // Deployment command (e.g., SSH or Ansible)
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Deploy to Staging Passed",
                         body: "The deployment to staging has passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Deploy to Staging Failed",
                         body: "The deployment to staging has failed.", attachLog: true
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Integration test command (e.g., Selenium or Cucumber)
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Integration Tests on Staging Passed",
                         body: "The integration tests on staging have passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Integration Tests on Staging Failed",
                         body: "The integration tests on staging have failed.", attachLog: true
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server...'
                // Deployment command (e.g., SSH or Ansible)
            }
            post {
                success {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Deploy to Production Passed",
                         body: "The deployment to production has passed successfully.", attachLog: true
                }
                failure {
                    emailext to: 'shanonudith@gmail.com',
                         subject: "Deploy to Production Failed",
                         body: "The deployment to production has failed.", attachLog: true
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed!'
            emailext to: 'shanonudith@gmail.com',
                 subject: "Pipeline Completed",
                 body: "The Jenkins pipeline has completed.", attachLog: true
        }
    }
}
