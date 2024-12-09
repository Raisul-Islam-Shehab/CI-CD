pipeline {
    agent any
    environment {
        name = 'Shehab'
    }
    stages {
        stage('Build') {
            steps {
                echo 'building...'
            }
        }
        stage('Test') {
            steps {
                echo 'testing...'
            }
        }
        stage('Deploy') {
            environment {
                name = 'Siam'
                job = 'student'
            }
            steps {
                echo 'deploying...'
                sh 'printenv'
            }
        }
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
        stage('PrintName') {
            steps {
                sh 'printenv'
            }
        }
        stage('Dockerfile') {
            agent {
                dockerfile true
            }
            steps {
                sh 'node --version'
                sh 'svn --version'
            }
        }
    }
}
