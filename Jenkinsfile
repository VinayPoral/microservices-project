pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerRegistry', toolName: 'docker') {
                        sh "docker build -t vinayporal/loadgenerator:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'DockerRegistry', toolName: 'docker') {
                        sh "docker push vinayporal/loadgenerator:latest"
                    }
                }
            }
        }
    }
}
