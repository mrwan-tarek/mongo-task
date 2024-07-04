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
            when { environment(name: "COMPOSE_STATUS", value: "0")  }
            steps {
                script {
                    sh "docker compose up -d "   
                }
            }
        }
    
        stage('do nothing if up') {
            when { environment(name: "COMPOSE_STATUS", value: "2")  }
            steps {
                script {
                    sh "echo 'already running' "   
                }
            }
        }
    }
}
