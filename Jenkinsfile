pipeline {
    agent any
    stages {
        stage('Example Build') {
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
