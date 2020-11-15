pipeline {

    agent {
        node {
            label 'master'
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
                echo '### Running Docker Linting Tools ###'

            }
        }

        stage('Build docker image') {
            steps {
                echo '### Building docker image ###'
            }
        }

        stage('Push image to registry') {
            steps {
                echo '### Pushing image to registry ###'
            }
        }

        stage('Deploy image to kubernetes cluster') {
            steps {
                echo '### Deploying image to kubernetes cluster ###'
            }
        }
    }
}
