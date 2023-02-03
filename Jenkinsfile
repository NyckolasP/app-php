pipeline {
    agent any
    stages {
	stage("verify tooling") {
	    steps {
		sh '''
		 docker info
		 docker version
		 /usr/local/bin/docker-compose version
		 curl --version
		 jq --version
		 '''
	    }	
	}
        stage("Start container") {
            steps {
                sh '/usr/local/bin/docker-compose up -d'
                sh '/usr/local/bin/docker-compose ps'
            }
        }
        stage("Run test container") {
            steps {
                sh 'curl localhost:200/create_db.php'
            }
        }
    }
}
