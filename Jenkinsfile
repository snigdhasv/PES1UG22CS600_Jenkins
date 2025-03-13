pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES1UG22CS600-1'
                sh 'g++ ./main/hello.cpp -o hello_exec'
                sh 'chmod +x hello_exec'
            }
        }
        stage('Test') {
            steps {
                sh './hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
