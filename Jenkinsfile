pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // bat 'mvn clean package'
            }
        }
        stage('Unit & Integration Tests') {
            steps {
                // bat 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                //  bat 'sonar-scanner.bat -Dsonar.projectKey=my-project'  
            }
        }       
        }
        stage('Security Scan') {
            steps {
                // bat 'dependency-check.bat --scan .'  
            }
        }
        stage('Deploy to Staging') {
            steps {
                // bat 'ansible-playbook deploy-staging.yml'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // bat 'newman run staging-tests.json'
            }
        }
        stage('Deploy to Production') {
            steps {
                // bat 'ansible-playbook deploy-production.yml'
            }
        }
}}
