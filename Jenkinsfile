pipeline {
    agent any

    environment {
        DOCKER_HOST = 'tcp://dind:2375'
    }

    stages {
        stage('Run Ubuntu Container in DinD') {
            steps {
                script {
                    // Pull an Ubuntu image from Docker Hub
                    sh 'docker pull ubuntu'

                    // Run a Docker container based on the pulled Ubuntu image
                    sh 'docker run -d --name my-ubuntu-container ubuntu'

                    // Execute commands inside the Docker container
                    sh 'docker exec my-ubuntu-container echo "Hello from Docker container!"'
                }
            }
        }
    }

    post {
        always {
            // Clean up: Stop and remove the Docker container
            script {
                sh 'docker stop my-ubuntu-container'
                sh 'docker rm my-ubuntu-container'
            }
        }
    }
}
