pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR_USERNAME/funny-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t funny-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f funny-container || true'
                sh 'docker run -d -p 8080:80 --name funny-container funny-site'
            }
        }
    }
}
