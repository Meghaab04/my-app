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
                scp -i /var/lib/jenkins/Ubuntu.pem -o StrictHostKeyChecking=no \
                target/dummy-java-app-1.0-SNAPSHOT.jar \
                ubuntu@3.6.94.109:/home/ubuntu/

                ssh -i /var/lib/jenkins/Ubuntu.pem -o StrictHostKeyChecking=no \
                ubuntu@3.6.94.109 \
                "pkill -f java || true && nohup java -jar /home/ubuntu/dummy-java-app-1.0-SNAPSHOT.jar > app.log 2>&1 &"
                '''
            }
        }
    }
}
