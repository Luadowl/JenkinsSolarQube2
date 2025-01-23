pipeline {
    agent any
    tools {
        maven 'Maven 3.x'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('SonarQube Analysis') {
            environment {
                SONAR_HOST_URL = 'http://172.17.0.3:9000'
                SONAR_AUTH_TOKEN = 'sqa_9a2d44d74c079a0ea07f949bf62590d1704d1e41'
            }
            steps {
                sh 'mvn sonar:sonar'
            }
        }
    }
}
