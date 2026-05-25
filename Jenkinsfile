pipeline {
    agent any

    stages {

        stage('Git Test') {
            steps {
                git 'https://github.com/Alok100-byte/JavaHelloWorld.git'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -lrt'
            }
        }
    }
}
