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
                
                // Install dependencies within the virtual environment
                sh 'pip install --user -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
