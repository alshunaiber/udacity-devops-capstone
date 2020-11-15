pipeline {

    agent {
        node {
            label 'nodejs'
        }
    }

    environment {
        APP_NAME = "books"
    }

    stages {

        stage('NPM Install') {
            steps {
                echo '### Installing NPM dependencies ###'
                sh '''
                        cd src
                        npm install
                   '''
            }
        }

        stage('Run Unit Tests') {
            steps {
                echo '### Running unit tests ###'
                sh 'cd src; npm test'
            }
        }

        stage('Run Nodejs Linting Tools') {
            steps {
                echo '### Running eslint on code ###'
                sh 'cd src; npm run lint'
            }
        }

        stage('Run Docker Linting Tools') {
            steps {
            }
        }

        stage('Build docker image') {
            steps {
            }
        }

        stage('Push image to registry') {
            steps {
            }
        }

        stage('Deploy image to kubernetes cluster') {
            steps {
            }
        }
    }
}
