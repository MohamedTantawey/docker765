pipeline {
    agent {
        label 'docker'
    }

    environment {
        DOCKER_BUILDKIT = '1'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mohamed/docker-react -f Dockerfile.dev .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'docker run --rm -e CI=true mohamed/docker-react npm run test'
            }
        }
    }
}
