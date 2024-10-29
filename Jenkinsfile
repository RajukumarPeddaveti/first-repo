pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/RajukumarPeddaveti/first-repo/'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('RajukumarPeddaveti/sample-app:v1')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image('RajukumarPeddaveti/sample-app:v1').inside {
                        sh 'node app.js'
                    }
                }
            }
        }
    }
}
