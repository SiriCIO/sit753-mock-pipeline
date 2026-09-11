pipeline {
    agent any

    triggers {
        // Polls GitHub every 5 minutes for new commits — satisfies the
        // 'triggered automatically after a new commit' requirement
        // without needing a webhook.
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Task: Compile and package the application code'
                echo 'Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Task: Run unit tests and integration tests to verify the application'
                echo 'Tool: JUnit (unit tests), Selenium (integration tests)'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Task: Analyse code quality against industry standards'
                echo 'Tool: SonarQube / SonarCloud'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Task: Scan code and dependencies for known vulnerabilities'
                echo 'Tool: OWASP Dependency-Check'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Task: Deploy the application to a staging server'
                echo 'Tool: AWS EC2 (via Ansible)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Task: Run integration tests on the staging environment'
                echo 'Tool: Postman / Newman'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Task: Deploy the verified build to the production server'
                echo 'Tool: AWS EC2 (via Ansible)'
            }
        }
    }
}
