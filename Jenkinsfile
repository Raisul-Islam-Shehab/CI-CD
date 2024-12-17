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
                sh 'python -m venv /venv1'
                sh '/venv1/bin/pip install --no-cache-dir -r requirements.txt'
                sh '/venv1/bin/python src/my_script.py'
            }
        }
    }
}
