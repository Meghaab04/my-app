pipeline {
    agent any

    tools {
        maven 'Maven'   // Configure this in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning code...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                echo 'Running app...'
                sh 'mvn exec:java'
            }
        }
    }

    post {
        success {
            echo 'Build SUCCESS!'
        }
        failure {
            echo 'Build FAILED!'
        }
    }
}
