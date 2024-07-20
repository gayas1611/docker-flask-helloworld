pipeline {
    agent any

    stages {
        stage('List Images Before Build') {
            steps {
                script {
                    sh 'docker image ls'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("my-flask-app")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("my-flask-app").run("-p 8080:8080 --name flask-container")
                }
            }
        }

        stage('List Images After Build and Run') {
            steps {
                script {
                    sh 'docker image ls'
                }
            }
        }
    }
}

