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

                sh 'echo $USER'

                sh 'python -m venv myvenv'

                sh 'ls -al'
                
                sh 'source myvenv/bin/activate'

                // Install dependencies within the virtual environment
                sh 'pip install -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
