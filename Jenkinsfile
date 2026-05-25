pipeline {
    agent any

    stages {

        stage('Checkout') {
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
                sh 'java -jar target/JavaHelloWorld-1.0.jar'
            }
        }
    }
}
