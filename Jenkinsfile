pipeline {
    agent any
    tools {
        maven 'M390'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                script {
        
                    def pom = readMavenPom file: 'pom.xml'
                    def artifactName = "${pom.artifactId}-${pom.version}.jar"

                    
                    sh "mkdir -p /opt/build-artifacts"

                    
                    sh "cp target/${artifactName} /opt/build-artifacts/"
                }
            }
        }
    }
}
