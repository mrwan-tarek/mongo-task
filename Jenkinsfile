pipeline {
    agent any

    stages {
        stage('Check Docker Compose status') {
            when {
                expression {
                    def containersCount  = sh(script: 'docker ps |grep compose-pipeline-* | wc -l', returnStdout: true)
                    containersCount.toInteger() == 2
                }
            }
            steps {
                script {
                    echo "Docker Compose is already running"
                    }
                }
            }
        stage('start Docker Compose') {
            when {
                expression {
                    def containersCount  = sh(script: 'docker ps |grep compose-pipeline-* | wc -l', returnStdout: true)
                    containersCount.toInteger() == 0
                }
            }
            steps {
                script {
                    echo "Docker Compose is not running, starting it now..."
                    sh "docker compose up -d"
                    }
                }
            }
        }
    }
