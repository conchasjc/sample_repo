pipeline {
    agent any

    stages {
        stage('Select Action') {
            steps {
                script {
                    // Choose which Taskfile task to run based on a parameter
                    def selectedTask = params.ACTION ?: "up"
                    echo "Running Taskfile action: ${selectedTask}"
                    
                }
            }
        }

        stage('Execute Action') {
            steps {
                echo 'Building project'
                sh "task ${selectedTask}"
            }
        }

        stage('Output Container Status') {
            steps {
                echo 'Running tests'
                sh 'docker ps -a'
            }
        }
    }

    parameters {
        choice(
            name: 'ACTION',
            choices: ['up', 'down', 'maintenance:on', 'maintenance:off', 'restart:grafana', 'restart:prometheus', 'restart:all'],
            description: 'Select which Taskfile action to run after git pull'
        )
    }
}
