pipeline {

    agent any

    tools {
        nodejs "nodejs"
    }

    environment {
        appName = "books"
        dockerUser= "faalsh"
        registryCredential = "docker_login"
        kubeCredential = "kube_login"
        kubeConfig = "config.yml"

        dockerImage = ""

    }

    stages {

        stage('test deploy') {
            steps {
                echo '### Deploying image to kubernetes cluster ###'
                // script {
                //     kubernetesDeploy(configs: ${kubeConfig}, kubeconfigId: ${kubeCredential})
                // }
            }
        }


        // stage('NPM Install') {
        //     steps {
        //         echo '### Installing NPM dependencies ###'
        //         sh '''
        //                 cd src
        //                 npm install
        //            '''
        //     }
        // }

        // stage('Run Unit Tests') {
        //     steps {
        //         echo '### Running unit tests ###'
        //         sh 'cd src; npm test'
        //     }
        // }

        // stage('Run Nodejs Linting Tools') {
        //     steps {
        //         echo '### Running eslint on code ###'
        //         sh 'cd src; npm run lint'
        //     }
        // }

        // stage('Run Docker Linting Tools') {
        //     agent {
        //         docker {
        //             image 'hadolint/hadolint:latest-debian'
        //         }
        //     }
        //     steps {
        //         echo '### Running Docker Linting Tools ###'
        //         sh 'hadolint dockerfiles/* | tee -a hadolint_lint.txt'
        //     }
        // }

        // stage('Build docker image') {
        //     steps {
        //         echo '### Building docker image ###'
        //         script {
        //         }
        //             kubeCredential = 'kube_login'
                    
        //             dockerImage = docker.build("${dockerUser}/${appName}:${BUILD_ID}", "./src")
        //     }
        // }

        // stage('Push image to registry') {
        //     steps {
        //         echo '### Pushing image to registry ###'
        //         script {
        //             docker.withRegistry( '', registryCredential ) { 
        //                 dockerImage.push("${BUILD_ID}")
        //                 kubeCredential = 'kube_login'
                        
        //                 dockerImage.push("latest")
        //             }
        //         }
        //     }
        // }

        // stage('Deploy image to kubernetes cluster') {
        //     steps {
        //         echo '### Deploying image to kubernetes cluster ###'
        //         script {
        //             kubernetesDeploy(configs: "hellowhale.yml", kubeconfigId: "mykubeconfig")
        //         }
        //     }
        // }
    }
}
