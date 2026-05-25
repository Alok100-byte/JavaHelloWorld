pipeline {

    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/Alok100-byte/JavaHelloWorld.git'
            }
        }

        stage('Build Maven Project') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Verify Target Folder') {
            steps {
                sh 'ls -lrt target'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sample-java-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f java-container || true'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:8080 --name java-container sample-java-app'
            }
        }

        stage('Verify Container') {
            steps {
                sh 'docker ps'
            }
        }
    }

    post {

        success {
            echo 'Pipeline executed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
