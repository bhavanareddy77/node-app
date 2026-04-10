pipeline {
    agent any

    environment {
        IMAGE_NAME = "node-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/bhavanareddy77/node-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 $IMAGE_NAME'
            }
        }
    }
}
