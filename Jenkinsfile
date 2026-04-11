pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh 'javac App.java'
            }
        }

        stage('Run') {
            steps {
                sh 'java App'
            }
        }
    }
}
