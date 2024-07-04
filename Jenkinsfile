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
                bat "set"
                script {
                      sh """
                        if [ $COMPOSE_STATUS -eq 2 ]
                        then
                          echo "starting the containers"
                          docker compose up -d
                        elif [ $COMPOSE_STATUS -eq 0 ]
                         then
                          echo "the contaires are already running"
                         fi
                        """
                    }
                }
        }
    }
}
