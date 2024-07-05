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

    }
}

