pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven...'
                sh 'mvn clean package'
            }
        }
        stage('Unit & Integration Tests') {
            steps {
                echo 'Running Tests with JUnit/TestNG...'
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube...'
                sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for vulnerabilities with OWASP...'
                sh 'dependency-check.sh --project myapp --scan .'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 Staging...'
                sh 'ansible-playbook deploy-staging.yml'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Postman/Selenium Tests...'
                sh 'newman run staging-tests.json'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 Production...'
                sh 'ansible-playbook deploy-production.yml'
            }
        }
    }
}