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
        //         // sh 'python --version'

        //         // sh 'pip --version'

        //         // sh 'ls -al'

        //         // sh 'id'

        //         // sh 'python -m venv venv'

        //         // sh 'ls -al'

        //         // sh '. venv/bin/activate'

        //         // Install dependencies within the virtual environment
        //         sh 'pip install --no-cache-dir -r requirements.txt'

        //         sh 'echo $PATH'

        //         // Run the Python script inside the virtual environment
        //         sh 'python src/my_script.py'
        //     }
        // }
        stage('TEST') {
            agent {
                dockerfile {
                    filename 'Dockerfile.build'
                }
            }
            steps {
                sh """
                python --version

                pip --version

                ls -al

                id

                python -m venv venv

                s -al

                . venv/bin/activate

                echo $VIRTUAL_ENV

                which python

                which pip

                pip install --upgrade pip

                // Install dependencies within the virtual environment
                pip install --no-cache-dir -r requirements.txt

                flake8 src

                // Run the Python script inside the virtual environment
                pytest --cov=src src/test_script.py
                """
            }
        }
    }
}
