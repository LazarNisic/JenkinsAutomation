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
                sh 'mvn clean package'
                echo 'Build stage done'
            }
        }

        stage('Deploy') {
            steps {
                script {
        
                    def pom = readMavenPom file: 'pom.xml'
                    def artifactName = "${pom.artifactId}-${pom.version}.jar"

                    
                    sh "mkdir -p /opt/build-artifacts"

                    
                    sh "cp target/${artifactName} /opt/build-artifacts/"

                    echo 'Deploy stage done'
                }
            }
        }
    }
}
