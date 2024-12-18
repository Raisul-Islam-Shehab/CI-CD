pipeline {
    agent none
    stages {
        // stage('BUILD') {
        //     agent {
        //         dockerfile {
        //             filename 'Dockerfile.build'
        //         }
        //     }
        //     steps {
        //         sh 'python --version'

        //         sh 'pip --version'

        //         sh 'ls -al'

        //         sh 'id'

        //         sh 'python -m venv venv'

        //         sh 'ls -al'

        //         sh '. venv/bin/activate'

        //         // Install dependencies within the virtual environment
        //         sh 'pip install --no-cache-dir -r requirements.txt'

        //         sh 'echo $PATH'

        //         // Run the Python script inside the virtual environment
        //         sh 'python src/my_script.py'
        //     }
        // }
        stage('TEST') {
            agent {
                // dockerfile {
                //     filename 'Dockerfile.build'
                // }
                docker {
                    image 'python:latest'
                }
            }
            steps {
                sh 'python --version'

                sh 'pip --version'

                sh 'ls -al'

                sh 'id'

                sh 'python -m venv venv'

                sh 'ls -al'

                sh '. venv/bin/activate && \
                    which python && \
                    which pip && \
                    pip install --no-cache-dir -r requirements.txt && \
                    echo $PATH && \
                    black src && \
                    flake8 src && \
                    pytest src/test_script.py'
            }
        }
    }
}
