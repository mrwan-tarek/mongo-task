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
    }
    stages {
        stage('compose up if shutdown') {
            when { expression { return env.COMPOSE_STATUS == 0 }
            steps {
                script {
                    sh "docker compose up -d "   
                }
            }
        }
    }
        stages {
        stage('do nothing if up') {
            when { expression { return env.COMPOSE_STATUS == 2 }
            steps {
                script {
                    sh "echo 'already running' "   
                }
            }
        }
    }
}
