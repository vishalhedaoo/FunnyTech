pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/vishalhedaoo/FunnyTech.git'
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
                sh 'docker run -d -p 8080:81 --name funny-container funny-site'
            }
        }
    }
}
