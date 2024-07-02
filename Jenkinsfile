pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "Hello $Name"
                docker compose -f mongo-compose.yaml up
            }
        }
    }
}
