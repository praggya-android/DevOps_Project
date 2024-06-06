pipeline {
    agent any

    // Configuration options
    options {
        buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '10'))
        timeout(time: 12, unit: 'HOURS')
        timestamps()
    }

    // Triggers
    triggers {
        cron('@midnight')
    }

    // Stages
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', credentialsId: '33522e2b-10de-4afd-8d5a-494f80daefdb', url: 'https://github.com/praggya-android/DevOps_Project.git'
            }
        }

        stage('Requirements') {
            steps {
                echo 'Installing requirements...'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Report') {
            steps {
                echo 'Reporting....'
            }
        }
    }

    // Post-build actions
    post {
        always {
            echo "This step will run after all other steps have finished. It will always run, even if the build status is not SUCCESS."
        }
    }
}
