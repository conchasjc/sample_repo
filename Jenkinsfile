pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project'
                sh 'task up'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests'
                sh 'docker ps -a'
            }
        }
    }
}
