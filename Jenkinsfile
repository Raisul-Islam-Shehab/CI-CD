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
        stage('New_Branch') {
            steps {
                echo 'I\'m in a new branch'
            }
        }
    }
}
