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
                bat 'mvn clean package'
                echo 'Build stage done'
            }
        }

        stage('Deploy') {
            steps {
                script {
        
                    def pom = readMavenPom file: 'pom.xml'
                    def artifactName = "${pom.artifactId}-${pom.version}.jar"

                    
                    bat "mkdir C:\\opt\\build-artifacts"

                    
                    bat "copy target\\${artifactName} C:\\opt\\build-artifacts\\"

                    echo 'Deploy stage done'
                }
            }
        }
    }
}
