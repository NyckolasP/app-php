pipeline {
    agent any
    stages {
        stage("Start container") {
            steps {
                sh 'docker compose up -d'
                sh 'docker compose ps'
            }
        }
        stage("Run test container") {
            steps {
                sh 'curl localhost:200/create_db.php'
            }
        }
    }
}
