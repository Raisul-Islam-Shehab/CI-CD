pipeline {
    agent none
    stages {
        stage('Run_Python_Script') {
            agent {
                dockerfile {
                    filename 'Dockerfile.build'
                }
            }
            steps {
                sh 'python --version'

                sh 'pip --version'

                sh 'ls -al'

                sh 'id'

                // Install dependencies within the virtual environment
                sh 'pip install -r requirements.txt'

                // Run the Python script inside the virtual environment
                sh 'python src/my_script.py'
            }
        }
    }
}
