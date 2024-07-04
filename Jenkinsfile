pipeline {
    agent any

    stages {
        stage('cheking containers') {
            steps {
                script {
                    sh "export COMPOSE_STATUS=`docker ps |grep compose-pipeline-* | wc -l` " 
                }
                echo "${COMPOSE_STATUS}"
            }
        }
        stage('compose up if shutdown') {
            steps {
                sh "printenv"
                script {
                    load "envvars.groovy" 
                   
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
