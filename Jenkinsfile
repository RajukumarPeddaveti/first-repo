pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/your-repo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('your-image-name')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image('your-image-name').inside {
                        sh 'node app.js'
                    }
                }
            }
        }
    }
}
