pipeline {
    agent any
pipeline {
    agent any
    stages {
        // Stage 1: Build
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        // Stage 2: Unit & Integration Tests
        stage('Unit & Integration Tests') {
            steps {
                bat 'mvn test'
            }
        }

        // Stage 3: Code Analysis
        stage('Code Analysis') {
            steps {
                bat 'sonar-scanner.bat -Dsonar.projectKey=my-project'
            }
        }

        // Stage 4: Security Scan
        stage('Security Scan') {
            steps {
                bat 'dependency-check.bat --scan .'
            }
        }

        // Stage 5: Deploy to Staging
        stage('Deploy to Staging') {
            steps {
                bat 'ansible-playbook deploy-staging.yml'
            }
        }

        // Stage 6: Integration Tests on Staging
        stage('Integration Tests on Staging') {
            steps {
                bat 'newman run staging-tests.json'
            }
        }

        // Stage 7: Deploy to Production
        stage('Deploy to Production') {
            steps {
                bat 'ansible-playbook deploy-production.yml'
            }
        }
    }
}    stages {
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
}
