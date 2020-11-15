pipeline {

    agent any

    tools {
        nodejs "nodejs"
    }

    environment {
        APP_NAME = "books"
        DOCKER_USER= 'faalsh'
        DOCKER_IMAGE = '' 
        registryCredential = 'docker_login' 
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
            agent {
                docker {
                    image 'hadolint/hadolint:latest-debian'
                }
            }
            steps {
                echo '### Running Docker Linting Tools ###'
                sh 'hadolint dockerfiles/* | tee -a hadolint_lint.txt'
            }
        }

        stage('Build docker image') {
            steps {
                echo '### Building docker image ###'
                script {
                    DOCKER_IMAGE = docker.build("${DOCKER_USER}/${APP_NAME}:${BUILD_NUMBER}", "./src")
                }
            }
        }

        stage('Push image to registry') {
            steps {
                echo '### Pushing image to registry ###'
                script {
                    docker.withRegistry( '', registryCredential ) { 
                        DOCKER_IMAGE.push() 
                    }
                }
            }
        }

        stage('Deploy image to kubernetes cluster') {
            steps {
                echo '### Deploying image to kubernetes cluster ###'
            }
        }
    }
}
