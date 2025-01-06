pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                    dockerfile {
                        filename 'Dockerfile.linux'
                        args '-u root'
                    }
            }
            steps {
                sh 'rm -rf ./Jenkinsfile && \
                npm run pack:linux && \
                npm run build:deb && \
                npm run build:deb-checksum'
            }
        }
    }
}
