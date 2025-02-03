pipeline {
    agent any
    // triggers {
    //     pollSCM('*/5 * * * *')
    // }
    stages {
        // stage('checkout') {
        //     steps {
        //         checkout scmGit(
        //         branches: [[name: 'when_directive']],
        //         userRemoteConfigs: [[url: 'https://github.com/Raisul-Islam-Shehab/CI-CD.git']])
        //     }
        // }
        stage('Example Build') {
            when {
                branch 'when_directive'  // only works on a multi-branch pipeline
            }
            steps {
                echo 'Hello World'
                echo 'Hi'
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
            steps {
                echo 'Hello triggers'
                echo 'new commit'
                echo 'new tag'
            }
        }
        stage('checking tag') {
            when {
                tag 'v*'
            }
            steps {
                echo 'checking if tag is building'
            }
        }
    }
}
