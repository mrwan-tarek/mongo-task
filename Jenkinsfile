pipeline {
    agent any

    stages {
        stage('cheking containers') {
            steps {
                script {
                    sh "COMPOSE_STATUS=`docker ps |grep compose-pipeline-* | wc -l`"   
                }
            }
        }
        stage('compose up if shutdown') {
            steps {
                script {
                    sh"""
                    if ($COMPOSE_STATUS == 0) {
                    echo 'running the containers now!!!!'
                    docker compose up -d
                    } elif ($COMPOSE_STATUS == 2) {
                    echo 'the containers are already running'
                        }"""
                    }
                }
        }
    }
}
