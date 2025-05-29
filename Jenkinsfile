pipeline {
    agent any

    tools {
        maven 'Maven_3.9.9'   // Make sure this matches the name in Jenkins -> Global Tool Configuration
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
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}