pipeline {
    agent any
    parameters {
        choice(name: 'CHOICE', choices: ['one', 'two', 'three'], description: 'Choose one')
    }
    stages {
        stage('Build') {
            steps {
                echo "Choice: ${params.CHOICE}"
            }
        }
    }
}
