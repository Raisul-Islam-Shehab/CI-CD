pipeline {
    agent any
    triggers {
        pollSCM('*/5 * * * *')
    }
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
                changeRequest target: 'main'
            }
            steps {
                echo 'Deploying'
            }
        }
        stage('build tag') {
            when {
                buildingTag()
            }
            steps {
                echo 'Building a Tag'
            }
        }
        stage('checking pollSCM') {
            when {
                buildingTag()
            }
            steps {
                echo 'Checking if pollSCM works'
            }
        }
        stage('checking using commit') {
            echo 'Hello triggers'
        }
    }
}
