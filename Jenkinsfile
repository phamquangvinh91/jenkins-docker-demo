pipeline {
    agent any

    stages {
        stage('Clone code') {
            steps {
                echo 'Đang clone mã nguồn...'
                checkout scm
            }
        }

        stage('Build Docker image') {
            steps {
                script {
                    docker.build('jenkins-docker-demo')
                }
            }
        }

        stage('Run Docker container') {
            steps {
                script {
                    sh "docker run -d -p 8090:80 --name demo_app jenkins-docker-demo"
                }
            }
        }
    }
}
