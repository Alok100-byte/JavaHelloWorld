pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -cp target/JavaHelloWorld-1.0.jar App'
            }
        }
        stage('Run Docker container') {
            steps {
                sh 'docker run -itd -p 8080:80 --name my-container my-image-app'
            }
        }
        stage('Verify container') {
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
