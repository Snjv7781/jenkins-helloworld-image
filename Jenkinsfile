pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/snjv7781/jenkins-helloworld-image.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("helloworld-image:${env.BUILD_NUMBER}")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("helloworld-image:${env.BUILD_NUMBER}").inside {
                        sh 'echo Hello, World from Docker container!'
                    }
                }
            }
        }
    }
}

