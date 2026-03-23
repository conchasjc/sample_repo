pipeline {
    
    agent {
        label 'built-in'
    }


    parameters {
        choice(
            name: 'ACTION',
            choices: ['up', 'down', 'maintenance:on', 'maintenance:off', 'restart:grafana', 'restart:prometheus', 'restart:all'],
            description: 'Select which Taskfile action to run'
        )
    }

    stages {
        stage('Select Action') {
            steps {
                echo "Selected Taskfile action: ${params.ACTION}"
            }
        }

        stage('Execute Action') {
            steps {
                echo "Executing Taskfile action..."
                sh "task ${params.ACTION}"
            }
        }

        stage('Output Container Status') {
            steps {
                echo 'Showing Container Status'
                sh 'docker ps -a'
            }
        }
    }
}
