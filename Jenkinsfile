pipeline {
    agent any

    environment {
        IMAGE_NAME = "my-spring-app"
        CONTAINER_NAME = "devops1"
        DOCKER_PORT = "9090"
        APP_PORT = "8082"  // Use the port your app listens to inside container
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target\\*.jar', fingerprint: true
            }
        }
    }
}
