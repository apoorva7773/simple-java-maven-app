pipeline {
    agent any

    tools {
        maven 'Maven_3.9.9'  // Use the name you configured in Jenkins Global Tool Config
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

        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
