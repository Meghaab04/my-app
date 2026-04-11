pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to EC2') {
            steps {
                sh '''
                scp -i C:\Users\megha\Downloads\Ubuntu.pem -o StrictHostKeyChecking=no \
                target/*.jar ubuntu@ec2-3-110-179-87:/home/ubuntu/

                ssh -i C:\Users\megha\Downloads\Ubuntu.pem -o StrictHostKeyChecking=no ubuntu@ec2-3-110-179-87 \
                "pkill -f java || true && nohup java -jar *.jar > app.log 2>&1 &"
                '''
            }
        }
    }
}
