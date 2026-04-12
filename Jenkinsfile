pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
                sh 'ls -l target/'
            }
        }
        stage('Deploy') {
    steps {
        sh 'scp -i /var/lib/jenkins/Ubuntu.pem -o StrictHostKeyChecking=no target/*.jar ubuntu@3.6.94.109:/home/ubuntu/'
            }
        }

        
    }
}
