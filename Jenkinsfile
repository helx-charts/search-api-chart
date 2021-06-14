pipeline {
    agent {
        kubernetes {
            cloud 'kubernetes'
            label 'agent-docker'
            defaultContainer 'agent-docker'
        }
    }
    stages {
        stage('Install') {
            steps {
                sh '''
                echo "Install"
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                echo "Test"
                '''
            }
        }
        stage('Publish') {
            when {
                buildingTag()
            }
//             environment {
//             }
            steps {
                sh '''
                echo "Publish"
                '''
            }
        }
    }
}