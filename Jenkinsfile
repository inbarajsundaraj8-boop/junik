pipeline {
    agent any

    tools {
        jdk 'JDK8'
        maven 'Maven3'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building application'
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running JUnit tests'
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                bat 'mkdir C:\\deploy'
                bat 'copy target\\HelloJenkins-1.0.jar C:\\deploy'
            }
        }
    }

    post {
        success {
            echo 'Build, Test and Deployment completed successfully'
        }
        failure {
            echo 'Build/Test failed – Deployment skipped'
        }
    }
}
