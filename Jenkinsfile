pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                // Maven build command (if applicable)
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
                    
                       mail to: 'shanonudith@gmail.com',
                        subject: "Unit and Integration Tests Passed",
                        body: "The unit and integration tests have passed successfully."
                        // attachmentsPattern: 'F:/Deakin Masters Studies/2nd Sem/profe/Jenkinsfile/continuous_delivery_pipeline_task6.1C/test-reports/test-reports.txt'
                    
                }
                failure {
                    
                       mail to: 'shanonudith@gmail.com',
                        subject: "Unit and Integration Tests Failed",
                        body: "The unit and integration tests have failed."
                        // attachmentsPattern: 'F:/Deakin Masters Studies/2nd Sem/profe/Jenkinsfile/continuous_delivery_pipeline_task6.1C/test-reports/test-reports.txt'
                    
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
                // SonarQube analysis command
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning code for security vulnerabilities...'
                // OWASP Dependency-Check command
            }
            post {
                success {
                   
                       mail to: 'shanonudith@gmail.com',
                        subject: "Security Scan Passed",
                        body: "The security scan has passed successfully."
                        // attachmentsPattern: 'F:/Deakin Masters Studies/2nd Sem/profe/Jenkinsfile/continuous_delivery_pipeline_task6.1C/security-reports/security-reports.txt'
                   
                }
                failure {
                   
                       mail to: 'shanonudith@gmail.com',
                        subject: "Security Scan Failed",
                        body: "The security scan has failed."
                        // attachmentsPattern: 'F:/Deakin Masters Studies/2nd Sem/profe/Jenkinsfile/continuous_delivery_pipeline_task6.1C/security-reports/security-reports.txt'
                    
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server...'
                // Deployment command (e.g., SSH or Ansible)
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Integration test command (e.g., Selenium or Cucumber)
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server...'
                // Deployment command (e.g., SSH or Ansible)
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
