pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                sh 'mvn clean install'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
                        archiveArtifacts artifacts: 'build-logs/build.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Build Stage Passed",
                                 body: "The build stage has completed successfully.",
                                 attachmentsPattern: 'build-logs/build.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/build.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Build Stage Failed",
                                 body: "The build stage has failed.",
                                 attachmentsPattern: 'build-logs/build.log'
                    }
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests...'
                sh 'mvn test > build-logs/test.log'
                echo 'Running integration tests...'
                sh 'mvn verify >> build-logs/test.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/test.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Unit and Integration Tests Passed",
                                 body: "The unit and integration tests have passed successfully.",
                                 attachmentsPattern: 'build-logs/test.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/test.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Unit and Integration Tests Failed",
                                 body: "The unit and integration tests have failed.",
                                 attachmentsPattern: 'build-logs/test.log'
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using SonarQube...'
                sh 'mvn sonar:sonar > build-logs/sonar.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/sonar.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Code Analysis Passed",
                                 body: "The code analysis has passed successfully.",
                                 attachmentsPattern: 'build-logs/sonar.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/sonar.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Code Analysis Failed",
                                 body: "The code analysis has failed.",
                                 attachmentsPattern: 'build-logs/sonar.log'
                    }
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning code for security vulnerabilities...'
                sh 'dependency-check.sh -s . > build-logs/security-scan.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/security-scan.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Security Scan Passed",
                                 body: "The security scan has passed successfully.",
                                 attachmentsPattern: 'build-logs/security-scan.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/security-scan.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Security Scan Failed",
                                 body: "The security scan has failed.",
                                 attachmentsPattern: 'build-logs/security-scan.log'
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to staging server...'
                sh 'deploy.sh staging > build-logs/deploy-staging.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/deploy-staging.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Deploy to Staging Passed",
                                 body: "The deployment to staging has passed successfully.",
                                 attachmentsPattern: 'build-logs/deploy-staging.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/deploy-staging.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Deploy to Staging Failed",
                                 body: "The deployment to staging has failed.",
                                 attachmentsPattern: 'build-logs/deploy-staging.log'
                    }
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                sh 'run-integration-tests.sh staging > build-logs/integration-tests-staging.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/integration-tests-staging.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Integration Tests on Staging Passed",
                                 body: "The integration tests on staging have passed successfully.",
                                 attachmentsPattern: 'build-logs/integration-tests-staging.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/integration-tests-staging.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Integration Tests on Staging Failed",
                                 body: "The integration tests on staging have failed.",
                                 attachmentsPattern: 'build-logs/integration-tests-staging.log'
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to production server...'
                sh 'deploy.sh production > build-logs/deploy-production.log'
            }
            post {
                success {
                    script {
                        archiveArtifacts artifacts: 'build-logs/deploy-production.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Deploy to Production Passed",
                                 body: "The deployment to production has passed successfully.",
                                 attachmentsPattern: 'build-logs/deploy-production.log'
                    }
                }
                failure {
                    script {
                        archiveArtifacts artifacts: 'build-logs/deploy-production.log', allowEmptyArchive: true
                        emailext to: 'shanonudith@gmail.com',
                                 subject: "Deploy to Production Failed",
                                 body: "The deployment to production has failed.",
                                 attachmentsPattern: 'build-logs/deploy-production.log'
                    }
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed!'
            script {
                archiveArtifacts artifacts: 'build-logs/*.log', allowEmptyArchive: true
                emailext to: 'shanonudith@gmail.com',
                         subject: "Pipeline Completed",
                         body: "The Jenkins pipeline has completed.",
                         attachmentsPattern: 'build-logs/*.log'
            }
        }
    }
}





// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building the code using Maven...'
//                 // Maven build command (if applicable)
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Build Stage Passed",
//                          body: "The build stage has completed successfully.", attachLog:true
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Build Stage Failed",
//                          body: "The build stage has failed."
//                 }
//             }
//         }
//         stage('Unit and Integration Tests') {
//             steps {
//                 echo 'Running unit tests...'
//                 // Unit test command (e.g., mvn test)
//                 echo 'Running integration tests...'
//                 // Integration test command (e.g., mvn integration-test)
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Unit and Integration Tests Passed",
//                          body: "The unit and integration tests have passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Unit and Integration Tests Failed",
//                          body: "The unit and integration tests have failed."
//                 }
//             }
//         }
//         stage('Code Analysis') {
//             steps {
//                 echo 'Analyzing code using SonarQube...'
//                 // SonarQube analysis command
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Code Analysis Passed",
//                          body: "The code analysis has passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Code Analysis Failed",
//                          body: "The code analysis has failed."
//                 }
//             }
//         }
//         stage('Security Scan') {
//             steps {
//                 echo 'Scanning code for security vulnerabilities...'
//                 // OWASP Dependency-Check command
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Security Scan Passed",
//                          body: "The security scan has passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Security Scan Failed",
//                          body: "The security scan has failed."
//                 }
//             }
//         }
//         stage('Deploy to Staging') {
//             steps {
//                 echo 'Deploying the application to staging server...'
//                 // Deployment command (e.g., SSH or Ansible)
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Staging Passed",
//                          body: "The deployment to staging has passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Staging Failed",
//                          body: "The deployment to staging has failed."
//                 }
//             }
//         }
//         stage('Integration Tests on Staging') {
//             steps {
//                 echo 'Running integration tests on staging environment...'
//                 // Integration test command (e.g., Selenium or Cucumber)
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Integration Tests on Staging Passed",
//                          body: "The integration tests on staging have passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Integration Tests on Staging Failed",
//                          body: "The integration tests on staging have failed."
//                 }
//             }
//         }
//         stage('Deploy to Production') {
//             steps {
//                 echo 'Deploying the application to production server...'
//                 // Deployment command (e.g., SSH or Ansible)
//             }
//             post {
//                 success {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Production Passed",
//                          body: "The deployment to production has passed successfully."
//                 }
//                 failure {
//                     mail to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Production Failed",
//                          body: "The deployment to production has failed."
//                 }
//             }
//         }
//     }
//     post {
//         always {
//             echo 'Pipeline completed!'
//             mail to: 'shanonudith@gmail.com',
//                  subject: "Pipeline Completed",
//                  body: "The Jenkins pipeline has completed."
//         }
//     }
// }
