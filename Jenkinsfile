pipeline {
    agent none
    stages {
        stage('Run_Python_Script') {
            agent {
                docker {
                    image 'python:latest'
                    // args '-u root'
                }
            }
            steps {
                sh 'python --version'

                sh 'pip --version'

                sh 'ls -al'

                sh 'id'

                sh 'sudo ls -al'

                // Install dependencies within the virtual environment
                sh 'pip install -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
