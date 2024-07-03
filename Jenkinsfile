pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    echo "Hello $Name"
                    sh "docker compose -f mongo-compose.yaml up"   
                }
            }
        }
    }
}
