pipeline {
    agent { label 'workers' }
    stages {
        stage('hello') {
            steps {
                echo 'Hello World!!!'
            }
        }
        stage('cat') {
            when {
                expression {
                    return env.BRANCH_NAME == 'master' || env.BRANCH_NAME == 'develop' || env.BRANCH_NAME == 'production'
                }
            }
            steps {
                script {
                    if (env.BRANCH_NAME == 'master') {
                        echo 'Hello from master!'
                    } else if (env.BRANCH_NAME == 'develop') {
                        echo 'Hello from develop!'
                    } else if (env.BRANCH_NAME == 'production') {
                        echo 'Hello from production!'
                    }
                }
            }
        }
    }
}

