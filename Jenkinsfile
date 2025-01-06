pipeline {
    agent any
    stages {
        stage('Example Build') {
            when {
                branch 'when_directive'
            }
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'syntax_branch'
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
