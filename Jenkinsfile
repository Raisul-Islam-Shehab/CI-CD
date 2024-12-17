pipeline {
    agent none
    stages {
        stage('Run_Python_Script') {
            agent {
                docker {
                    image 'python:latest'
                }
            }
            steps {
                sh 'python --version'
                sh 'pip install --no-cache-dir -r requirements.txt'
                sh 'python src/my_script.py'
            }
        }
    }
}
