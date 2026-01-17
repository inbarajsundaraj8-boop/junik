pipeline {
    agent any

    tools {
        jdk 'JDK8'
        maven 'Maven3'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Compiling project'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running JUnit tests'
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'JUnit tests passed successfully'
        }
        failure {
            echo 'JUnit tests failed'
        }
    }
}
