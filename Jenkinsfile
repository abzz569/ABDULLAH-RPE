pipeline{
    agent any
    stages{
        stage('Builds') {
            steps {
                echo 'Building the code using Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using JUnit and Selenium'
            }
            post{
                always{
                    emailext (
                        subject: 'Unit and Integration Tests Status',
                        to: 'abdullahazad483@gmail.com',
                        body: "${currentBuild.result}: Job ",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code using Jenkins and SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing a security scan on the code using OWASP ZAP'
            }
            post{
                always{
                    emailext (
                        subject: 'Security Scan Status',
                        to: 'abdullahazad483@gmail.com',
                        body: "${currentBuild.result}: Job ",
                        attachLog: true,
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying the application to an AWS EC2 instance'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on the staging environment using Selenium'
            }
            post{
                always{
                    emailext (
                        subject: 'Integration Tests on Staging Status',
                        to: 'abdullahazad483@gmail.com',
                        body: "${currentBuild.result}: Job ",
                        attachLog: true,
                    )
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying the application to an AWS EC2 instance'
            }
        }
    }

}
