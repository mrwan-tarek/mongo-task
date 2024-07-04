pipeline {
    agent any

    stages {
        stage('cheking containers') {
            steps {
                script {
                    sh "COMPOSE_STATUS=`docker ps |grep compose-pipeline-* | wc -l`"
                    sh """ echo "env.COMPOSE_STATUS=${COMPOSE_STATUS}"  >> envvars.groovy """
                }
            }
        }
        stage('compose up if shutdown') {
            steps {
                script {
                    load "envvars.groovy" 
                    sh "printenv"
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
