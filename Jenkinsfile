pipeline {
    agent none
    stages {
        stage('BUILD') {
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

                sh 'python -m venv venv'

                sh 'ls -al'

                sh '. venv/bin/activate && \
                    which python && \
                    python --version && \
                    which pip && \
                    pip --version && \
                    pip install -r requirements.txt && \
                    echo $PATH && \
                    black src && \
                    flake8 src && \
                    python src/my_script.py'
            }
        }
        stage('TEST') {
            agent {
                docker {
                    image 'python:3.13-alpine3.21'
                }
            }
            steps {
                sh 'python --version'

                sh 'pip --version'

                sh 'id'

                sh 'python -m venv venv'

                sh 'ls -al'

                sh '. venv/bin/activate && \
                    which python && \
                    which pip && \
                    pip install -r requirements.txt && \
                    echo $PATH && \
                    black src && \
                    flake8 src && \
                    pytest src/test_script.py'
            }
        }
    }

    post {
        always {
        echo 'Running post always'
        }
    }
}
