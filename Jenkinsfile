pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    echo "Hello"
                    sh "docker compose up -d"   
                }
            }
        }
    }
}
