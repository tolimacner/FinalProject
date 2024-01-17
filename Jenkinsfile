pipeline {
    agent any

    stages {
        stage('Run Docker Container') {
            steps {
                script {
                    // Pull a Docker image (e.g., 'ubuntu') from Docker Hub
                    docker.image('ubuntu').pull()

                    // Run a Docker container based on the pulled image
                    def myContainer = docker.container('my-ubuntu-container').withRun('-d -it ubuntu')

                    // Execute commands inside the Docker container
                    myContainer.inside {
                        // Print a message including the branch name
                        echo "Hello from Docker container on branch: \${env.BRANCH_NAME}"
                    }

                    
                }
            }
        }
    }
}
