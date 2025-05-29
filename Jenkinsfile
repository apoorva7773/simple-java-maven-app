pipeline {
    agent any

    tools {
        maven 'Maven3'  // Use the Maven version configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/apoorva7773/simple-java-maven-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Report') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
