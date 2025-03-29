pipeline {
    agent any
    tools {
        maven 'M390'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Checkout stage done'
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage done'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage done'
            }
        }
    }
}
