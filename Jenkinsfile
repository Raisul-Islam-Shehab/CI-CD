pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
                    docker --version
                    git --version
                    docker buildx version
                    docker buildx build --platform linux/amd64,linux/arm64 -t raisul716/kubekit --push .
                '''
            }
        }
    }
}

