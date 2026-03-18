pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project'
                sh 'sudo docker ps -a'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'task --version'
            }
        }
    }
}
