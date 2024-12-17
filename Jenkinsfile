pipeline {
    agent none
    stages {
        stage('Run_Python_Script') {
            agent {
                docker {
                    image 'python:3.13-alpine3.21'
                }
            }
            steps {
                sh 'python src/my_script.py'
            }
        }
    }
}
