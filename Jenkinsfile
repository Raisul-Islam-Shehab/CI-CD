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
                // Create a virtual environment
                sh 'python -m venv venv'

                // Activate the virtual environment
                sh '. venv/bin/activate'

                // Install dependencies within the virtual environment
                sh 'pip install -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
