pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Run') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }
}
