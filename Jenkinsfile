pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/snjv7781/jenkins-helloworld-image.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hello-world-image .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8081:80 hello-world-image'
            }
        }
    }
}

