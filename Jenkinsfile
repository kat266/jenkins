pipeline {
    agent any

    stages {
        stage('Checkout Git') {
            steps {
                checkout scm
            }
        }

        stage('Pull Content to Folder') {
            steps {
                bat '''
                    if not exist pulled-content mkdir pulled-content
                    copy *.txt pulled-content\\
                    copy README.md pulled-content\\
                '''
            }
        }

        stage('Verify Content') {
            steps {
                bat 'dir pulled-content'
            }
        }
    }
}