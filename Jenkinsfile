pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
        jdk "java"
    }

    stages {
        stage('compile') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vishnukant/DevOpsClassCodes.git'
                // Run Maven on a Unix agent.
                sh "mvn compile"
            }
        }
        
        stage('codereview') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vishnukant/DevOpsClassCodes.git'
                // Run Maven on a Unix agent.
                sh "mvn -P metrics pmd:pmd"
            }
        }
        
        stage('test') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vishnukant/DevOpsClassCodes.git'
                // Run Maven on a Unix agent.
                sh "mvn test"
            }
        }
        
        stage('metricjob') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vishnukant/DevOpsClassCodes.git'
                // Run Maven on a Unix agent.
                sh "mvn cobertura:cobertura -Dcobertura.report.format=xml"
            }
        }
        
        stage('package') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vishnukant/DevOpsClassCodes.git'
                // Run Maven on a Unix agent.
                sh "mvn package"
            }
        }
    }
}
