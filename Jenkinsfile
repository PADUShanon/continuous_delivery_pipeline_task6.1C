// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building the code using Maven...'
                
//             }
//             post {
//                 success {
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Build Stage Passed",
//                          body: "The build stage has completed successfully.", attachLog:true
//                 }
//                 failure {
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Build Stage Failed",
//                          body: "The build stage has failed.", attachLog: true
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
//                     emailext subject: 'Unit and Integration Tests Passed',
//                     body: 'The unit and integration tests have passed successfully.',
//                     to: 'shanonudith@gmail.com',
//                     attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext subject: 'Unit and Integration Tests Failed',
//                     body: 'The unit and integration tests have failed.',
//                     to: 'shanonudith@gmail.com',
//                     attachLog: true
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
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Code Analysis Passed",
//                          body: "The code analysis has passed successfully.", 
//                          attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Code Analysis Failed",
//                          body: "The code analysis has failed.", 
//                          attachLog: true
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
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Security Scan Passed",
//                          body: "The security scan has passed successfully.", 
//                          attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Security Scan Failed",
//                          body: "The security scan has failed.", 
//                          attachLog: true
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
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Staging Passed",
//                          body: "The deployment to staging has passed successfully.", 
//                          attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Staging Failed",
//                          body: "The deployment to staging has failed.", 
//                          attachLog: true
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
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Integration Tests on Staging Passed",
//                          body: "The integration tests on staging have passed successfully.", 
//                          attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Integration Tests on Staging Failed",
//                          body: "The integration tests on staging have failed.", 
//                          attachLog: true
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
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Production Passed",
//                          body: "The deployment to production has passed successfully.", 
//                          attachLog: true
//                 }
//                 failure {
//                     script {
//                         currentBuild.result = 'FAILURE'
//                     }
//                     emailext to: 'shanonudith@gmail.com',
//                          subject: "Deploy to Production Failed",
//                          body: "The deployment to production has failed.", 
//                          attachLog: true
//                 }
//             }
//         }
//     }
//     post {
//         always {
//             echo 'Pipeline completed!'
//             emailext to: 'shanonudith@gmail.com',
//                  subject: "Pipeline Completed",
//                  body: "The Jenkins pipeline has completed.", 
//                  attachLog: true
//         }
//     }
// }



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
 mail to: 'shanonudith@gmail.com',
 subject: "Build Stage Passed",
 body: "The build stage has completed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Build Stage Failed",
 body: "The build stage has failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Unit and Integration Tests Passed",
 body: "The unit and integration tests have passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Unit and Integration Tests Failed",
 body: "The unit and integration tests have failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Code Analysis Passed",
 body: "The code analysis has passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Code Analysis Failed",
 body: "The code analysis has failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Security Scan Passed",
 body: "The security scan has passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Security Scan Failed",
 body: "The security scan has failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Deploy to Staging Passed",
 body: "The deployment to staging has passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Deploy to Staging Failed",
 body: "The deployment to staging has failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Integration Tests on Staging Passed",
 body: "The integration tests on staging have passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Integration Tests on Staging Failed",
 body: "The integration tests on staging have failed."
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
 mail to: 'shanonudith@gmail.com',
 subject: "Deploy to Production Passed",
 body: "The deployment to production has passed successfully."
 }
 failure {
 mail to: 'shanonudith@gmail.com',
 subject: "Deploy to Production Failed",
 body: "The deployment to production has failed."
 }
 }
 }
 }
 post {
 always {
 echo 'Pipeline completed!'
 mail to: 'shanonudith@gmail.com',
 subject: "Pipeline Completed",
 body: "The Jenkins pipeline has completed."
 }
 }
}