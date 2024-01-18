
pipeline {
    agent any

    environment {
        DOCKER_HOST = 'tcp://docker:2376'
        DOCKER_CERT_PATH = '/certs/client'
        DOCKER_TLS_VERIFY = '1'
    }

    stages {
        stage('Run Ubuntu Container in DinD') {
            steps {
                script {
                    // Pull an Ubuntu image from Docker Hub
                    sh 'docker pull ubuntu'

                    // Run a Docker container based on the pulled Ubuntu image
                    sh 'docker run -d --name my-ubuntu-container ubuntu'
   
                }
            }
        }
    }   
}
