pipeline {
    agent any
    parameters {
        choice(name: 'CHOICE', choices: 'one\ntwo\nthree', description: 'Choose one')
    }
    stages {
        stage('Build') {
            steps {
                echo "Choice: ${params.CHOICE}"
            }
        }
    }
}
