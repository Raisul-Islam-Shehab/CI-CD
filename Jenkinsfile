pipeline {
    agent any
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
           steps {
                echo 'deploying...'
            }
        }
        stage('Example') {
            stages {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
    }
}