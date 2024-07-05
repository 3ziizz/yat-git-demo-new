pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Git'
            }
        }
	stage('print') {
            steps {
                echo "Hello from $name"
            }
        }
       stage('auto') {
            steps {
                echo "Automation 2"
            }
        }
        stage('build') {
            steps {
             	sh 'docker ps'
		sh 'docker ps --format "{{.Names}}"'
		script {
            		def existingContainers = sh(
               			 script: 'docker ps --format "{{.Names}}"',
                		 returnStdout: true
            			).trim()
            
            		if (existingContainers.contains('mongo-express') &&
                		existingContainers.contains('mongodb')) {
                		echo 'Containers already exist'
            		}else{
				sh 'docker compose up -d'
			}
		
        	}
        	
        	sh 'docker ps'
	    }
        }

    }
}

