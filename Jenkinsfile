pipeline {
    agent any

    tools {
        jdk 'jdk-17'       // Debe coincidir con Global Tool Configuration
        maven 'maven-3.9'  // Debe coincidir con Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/danyjosue493-pixel/demo-ci.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline ejecutado exitosamente.'
        }
        failure {
            echo 'El pipeline falló.'
        }
    }
}

