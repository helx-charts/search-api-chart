pipeline {
    agent {
        kubernetes {
            cloud 'kubernetes'
            label 'agent-docker'
            defaultContainer 'agent-docker'
        }
    }
    stages {
        stage('Publish') {
            when {
                buildingTag()
            }
            steps {
                sh '''
                cd lib
                git clone git@github.com:helx-charts/charts.git && cd charts
                git checkout feature/build-script
                ./bin/publish.sh search-api $TAG_NAME
                '''
            }
        }
    }
}