pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven'
                // Command to run Maven build tool
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests using JUnit'
                // Command to run JUnit test automation tool for unit tests
                echo 'Running integration tests using Selenium'
                // Command to run Selenium test automation tool for integration tests
            }
            post {
                always {
                    mail to: "Abdullahazad483@gmail.com",
                         subject: "Test Results",
                         body: "The master build is happy.\n\nConsole: ${env.BUILD_URL}.\n\n",
                        attachLog: true,
                        compressLog:true
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code using Jenkins plugin for Checkstyle'
                // Command to integrate Checkstyle plugin with Jenkins for code analysis
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Scanning code for vulnerabilities using OWASP ZAP'
                // Command to run OWASP ZAP tool for security scan
            }
            post {
                always {
                    emailext attachLog: true, body: "${currentBuild.result}: ${BUILD_URL}", compressLog: true, replyTo: 'abdullahazad483@gmail.com',
       subject: "Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}", to: 'abdullahazad483@gmail.com'
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to AWS EC2 instance for staging'
                // Command to deploy to AWS EC2 instance for staging
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging using Selenium'
                // Command to run Selenium test automation tool for integration tests on staging
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to AWS EC2 instance for production'
                // Command to deploy to AWS EC2 instance for production
            }
        }
    }
}
