pipeline {
    agent any
    stages {
	stage("verify tooling") {
	    steps {
		sh '''
		 docker info
		 docker version
		 yum install docker-compose-plugin
		 docker-compose version
		 curl --version
		 jq --version
		 '''
	    }	
	}
        stage("Start container") {
            steps {
                sh 'docker-compose up -d'
                sh 'docker-compose ps'
            }
        }
        stage("Run test container") {
            steps {
                sh 'curl localhost:200/create_db.php'
            }
        }
    }
}
