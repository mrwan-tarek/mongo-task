pipeline {
    agent any

    stages {
        stage('Check and Run Docker Compose') {
            steps {
                script {
                    // Check if Docker Compose is already running
                    def isrunning = sh(script: 'docker ps |grep compose-pipeline-* | wc -l', returnStdout: true)
                    def isRunning = isrunninng.toInteger()

                    echo "$isRunning"

                    if (isRunning == 2) {
                        echo "Docker Compose is already running"
                    } else {
                        // Docker Compose is not running, start it
                        echo "Docker Compose is not running, starting it now..."
                        sh 'docker compose up -d'
                    }
                }
            }
        }
    }
}
