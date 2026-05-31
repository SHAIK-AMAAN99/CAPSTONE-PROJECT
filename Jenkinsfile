pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-docker-app .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f html-app || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name html-app -p 80:80 html-docker-app'
            }
        }
    }
}
