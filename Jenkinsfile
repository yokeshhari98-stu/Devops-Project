pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'Devops1-name', url: 'https://github.com/yokeshhari98-stu/Devops-Project'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
