pipeline {
    agent none
    stages {
        stage('Run_Python_Script') {
            agent {
                docker {
                    image 'python:latest'
                    args '-u python'
                }
            }
            steps {
                sh 'python --version'

                sh 'pip --version'

                sh 'echo $USER'
                
                // sh 'python -m venv venv'
                
                // sh '. venv/bin/activate'

                // Install dependencies within the virtual environment
                sh 'pip install -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
