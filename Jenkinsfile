pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/Alok100-byte/JavaHelloWorld.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -cp target/JavaHelloWorld-1.0.jar'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-image-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -itd -p 8080:80 --name my-container my-image-app'
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
            echo 'Build completed successfully!'
        }

        failure {
            echo 'Build failed!'
        }
    }
}
